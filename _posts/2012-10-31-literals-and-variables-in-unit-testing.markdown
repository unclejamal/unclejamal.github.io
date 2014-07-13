---
layout: post
title: Literals and variables in unit testing
---
Today at the&nbsp;<a href="http://blog.path11.com/post/33827060379/goos-book-club-update">Path11 Book Club</a>&nbsp;we talked about chapters 21 and 22 of the book "Growing Object-Oriented Systems Guided By Tests" by S. Freeman and Nat Pryce.<br />
<br />
In the part Literals and Variables of the chapter 21 the authors advise to <b>use variables/constants in place of meaningless literals</b>:<br />
<blockquote class="tr_bq">
<i>...test code tends&nbsp;to be more concrete than production code, which means it has more literal values.&nbsp;Literal values without explanation can be difficult to understand because the&nbsp;programmer has to interpret whether a particular value is significant (e.g. just&nbsp;outside the allowed range) or just an arbitrary placeholder to trace behavior (e.g.&nbsp;should be doubled and passed on to a peer).</i><br />
<i>...</i><br />
<i>One solution is to allocate literal values to variables and constants with names&nbsp;that describe their function.</i></blockquote>
While this rule is rather self-explanatory, I have noticed some interesting pattern. When I do TDD pretty often in the refactoring phase I go through the test code and replace literals with constants (unless it obscures the readability). What happens is <b>2 kinds of constants emerge</b>:<br />
<ul>
<li><b>Example Constants</b> (one value&nbsp;out of many possible)</li>
</ul>
<blockquote class="tr_bq">
public static final String USER_NAME = "Joe"; //in fact it could be also "John" or "Sue"<br />
public static final int INVALID_ID = 666; //in fact it could be also 667, 668, 669 and so on...</blockquote>
<ul>
<li><b>Significant Constants</b> (concrete value having special meaning)</li>
</ul>
<blockquote class="tr_bq">
public static final String ATTR_EVENT_ID = "eventId"; //&nbsp;significant value<br />
public static final int AGE_OF_CONSENT = 18; //&nbsp;significant&nbsp;value</blockquote>
<b>Significant</b><b>&nbsp;Constants</b> will be very often needed in both test and implementation. So they can be moved to the implementation class and then referred to in the test class.<br />
<br />
On the other hand, <b>Example Constants</b> will usually stay only in the test code.<br />
<br />
Here is an example using Spring MVC:<br />
<blockquote class="tr_bq">
<script src="https://gist.github.com/3990091.js?file=ShowUserControllerTest.java"></script>
<script src="https://gist.github.com/3990268.js?file=ShowUserController.java"></script>
</blockquote>
<br />
Update: as pointed out in the comments, sharing Significant Constants in both tests and implementations carries the risk of uncaught errors when editing the constant value. The safest way is indeed to have the test class be entirely a specification, thus defining its own constants/variables and not refer to the implementation class.<br />
<br />
PS: don't forget to visit awesome&nbsp;<a href="http://blog.path11.com/post/33827060379/goos-book-club-update">Path11 Book Club</a>&nbsp;:)
