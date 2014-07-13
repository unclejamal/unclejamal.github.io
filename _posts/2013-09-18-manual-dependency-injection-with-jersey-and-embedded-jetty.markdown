---
layout: post
title: Manual dependency injection with Jersey and embedded Jetty
---
<div>
I wrote a little application demonstrating how to manually (through constructors) inject dependencies into Jersey resources in an embedded container like Jetty.&nbsp;</div>
<div>
<br /></div>
<div>
The benefits are:</div>
<div>
- lightweightness (no need to use Spring, Guice, etc.),</div>
<div>
- more control over your application (less magic behind the scenes),</div>
<div>
- controlling dependencies in tests (via Dependency Injection)</div>
<div>
- running a web app with a simple Java main method (via embedded Jetty)</div>
<div>
<br /></div>
<div>
The example application is called Time Expert. It exposes the current time via a RESTful web service, so when I run it in the production (via <i>Main.java</i>) I can use it as following:</div>
<blockquote class="tr_bq">
<script src="https://gist.github.com/unclejamal/6615253.js"></script></blockquote>
<div>
<br /></div>
<div>
Here's how I test it&nbsp;(<i>TimeAcceptanceTest.java</i>)&nbsp;:</div>
<div>
<blockquote class="tr_bq">
<span style="font-family: Courier New, Courier, monospace;">
<script src="https://gist.github.com/unclejamal/6615299.js"></script></span></blockquote>
</div>
<div>
<br /></div>
<div>
However, &nbsp;I cannot rely here on the real time because it changes every time I run tests . The problem can be easily solved with the Clock pattern. My tests require a <i>FixedClock</i> which allows me to set the current time to any value:</div>
<div>
<br /></div>
<script src="https://gist.github.com/unclejamal/6615321.js"></script><br />
<div>
<br /></div>
<div>
&nbsp;So I start my server with a fixed clock:</div>
<div>
<blockquote class="tr_bq">
<span style="font-family: Courier New, Courier, monospace;"><script src="https://gist.github.com/unclejamal/6615340.js"></script></span></blockquote>
</div>
<div>
<br /></div>
<div>
<br /></div>
<div>
... and then set it to, say, 20:15:</div>
<div>
<br /></div>
<div>
<blockquote class="tr_bq">
<span style="font-family: Courier New, Courier, monospace;"><script src="https://gist.github.com/unclejamal/6615367.js"></script></span></blockquote>
</div>
<div>
<br /></div>
<div>
Since my Jersey resource class is only aware of the clock interface, it will display 20:15:</div>
<div>
<br /></div>
<div>
<blockquote class="tr_bq">
<span style="font-family: Courier New, Courier, monospace;"><script src="https://gist.github.com/unclejamal/6615383.js"></script></span></blockquote>
</div>
<div>
<span style="font-family: Courier New, Courier, monospace;"><br /></span></div>
<div>
In order to create your Jersey resources with manually injected dependencies you have to register&nbsp;<i>org.glassfish.jersey.servlet.ServletContainer</i> with a customized <i>org.glassfish.jersey.server.ResourceConfig</i>. In that config Jersey resources can be newed up with their dependencies:</div>
<div>
<blockquote class="tr_bq">
<span style="font-family: Courier New, Courier, monospace;"><script src="https://gist.github.com/unclejamal/6615427.js"></script></span></blockquote>
</div>
<div>
<br /></div>
<div>
Of course the production provides a real clock (which returns <i>new Date()</i>):</div>
<div>
<br /></div>
<div>
<blockquote class="tr_bq">
<span style="font-family: Courier New, Courier, monospace;"><script src="https://gist.github.com/unclejamal/6615449.js"></script></span></blockquote>
</div>
<div>
<br /></div>
<div>
Code is available under:&nbsp;<a href="https://github.com/unclejamal/TimeMaster">https://github.com/unclejamal/TimeMaster</a></div>
<div>
<br /></div>
<div>
Enjoy!</div>
<div>
<br /></div>
<div>
Tested using:</div>
<div>
- Java 1.7,</div>
<div>
- Gradle 1.7 (easily convertible to Maven :)),</div>
<div>
- Jersey 2.2,</div>
<div>
- Jetty 9.0.5.</div>

