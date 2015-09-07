---
layout: post
title: Primitive exceptions
---

In my experience many programmers seem to agree that [Primitive Obsession](http://c2.com/cgi/wiki?PrimitiveObsession) can be a bad thing in more complicated projects. The risk is it might lead for related behaviour to be scattered around the system which inevitably leads to lower programmer's understanding, duplicated code, inconsistent behaviour (when the duplicated code is not updated everywhere).

For example:
{% highlight java %}
  public static void main(String[] args) {
    extractFirstName("Mr Pawel A. Duda"); // should yield Pawel
    extractLastName("Mr Pawel A. Duda"); // should yield Duda

    extractFirstName("Duda, Pawel"); // should yield Pawel
    extractLastName("Duda, Pawel"); // should yield Duda
  }

  public static String extractFirstName(String name) {
     // DUPLICATED: understanding the structure of name 
  }
  
  public static String extractLastName(String name) {
     // DUPLICATED: understanding the structure of name 
  }
}
{% endhighlight %}

Because I am passing Strings around in the system, many places will need to duplicate the logic of understanding the String and then parsing some data out of it.

Alternatively, I could have converted the String into a domain object as soon as possible:
{% highlight java %}
  public static void main(String[] args) {
    Person person1 = convertToPerson("Mr Pawel A. Duda");
    Person person2 = convertToPerson("Duda, Pawel");

    person1.getFirstName(); // should yield Pawel
    person1.getLastName(); // should yield Duda
    
    person2.getFirstName(); // should yield Pawel
    person2.getLastName(); // should yield Duda
  }

  public static Person convertToPerson(String name) {
     // understanding the structure of name (in just one place)
  }
}
{% endhighlight %}


Here is an example of the most common approach I see:
{% highlight java %}
public class CommonApproach {
    public static void main(String[] args) {
        new CommonUi(new CommonService()).addNumbers(1, 2, 3, 4, 5, 6);
    }

    public static class CommonUi {
        private CommonService commonService;

        public CommonUi(CommonService commonService) {
            this.commonService = commonService;
        }

        public void addNumbers(int... numbers) {
            try {
             System.out.println(commonService.addNumbers(numbers));
            } catch (RuntimeException e) {
                System.out.println(e.getMessage());
            }
        }
    }

    public static class CommonService {
        public int addNumbers(int[] numbers) {
            if (numbers.length > 5) throw new RuntimeException("Service supports only up to 5 numbers, but was " + numbers.length);

            int sum = 0;
            for (int number : numbers) {
                sum += number;
            }
            return sum;
        }
    }
}
{% endhighlight %}


But what about ordinary integer-based loops?
--------------------------

Now.


Summary
--------------------------

But enough about Ruby. I am simply wondering how successful the new Java 8 syntax will be in replacing the old habits of Java programmers... I am guessing this will be the case for collections processing. Again, I see a lot written on that. But I suppose the strongest habit, 'for' loops for plain old integer-based loops might stay on. Just a guess... We will see :)

Which syntax do you prefer?
