---
layout: post
title: BDD with Robot Framework and Java
---
<div style="text-align: justify;">
<div style="text-align: left;">
Inspired by Matt Wynne's podcast&nbsp;<a href="http://skillsmatter.com/podcast/agile-scrum/bdd-as-its-meant-to-be-done">"BDD as it's meant to be done"</a>&nbsp;I reproduced his sample application with usage of Robot Framework and Java (in place of Cucumber and Ruby). This post is intented to give an overview of a possible setup for Java-based BDD (<a href="https://github.com/unclejamal/CashDispenser">source code</a>).</div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
<br /></div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
<b>Idea</b></div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
<br /></div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
According to Gojko Adzic, 90% of teams that fail with ATDD don't structure they tests properly which results in so called scripts (dozens of test code lines which mix up specification, workflow, user interface) that are a extremly difficult to mantain. The tests should answer the question '<i>what</i>' to test as opposed to '<i>how</i>' to do it.</div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
<br /></div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
Matt suggests to structure acceptance tests in a layered stack (I rephrased the layer names):</div>
</div>
<div style="text-align: left;">
<br /></div>
<div class="separator" style="clear: both; text-align: center;">
<a href="http://1.bp.blogspot.com/-U1cm6wL6FYs/TtahWK0i3OI/AAAAAAAAA6o/TMk5NwWf_xc/s1600/bdd-layers.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="240" src="http://1.bp.blogspot.com/-U1cm6wL6FYs/TtahWK0i3OI/AAAAAAAAA6o/TMk5NwWf_xc/s320/bdd-layers.png" width="320" /></a></div>
<div style="text-align: left;">
<br /></div>
<div style="text-align: justify;">
<div style="text-align: left;">
</div>
<ul>
<li><i>Examples </i>- table-based set of input values introduced to the system and expected output values upon performing some action</li>
<li><i>Scenario </i>- Given-When-Then style of describing the action from <i style="text-align: justify;">Examples</i><span class="Apple-style-span" style="text-align: justify;">&nbsp;step-by-step</span></li>
<li><i>Steps </i>- detailed definition of <i style="text-align: justify;">Scenario </i><span class="Apple-style-span" style="text-align: justify;">steps kept in an technology-independent manner</span></li>
<li><i>Glue </i>- glue code connecting tests with the app itself (uses domain or interface classes in order to manipulate the <i style="text-align: justify;">Application</i><span class="Apple-style-span" style="text-align: justify;">)</span></li>
<li><i>Application </i>- the application itself (should work according to the <i style="text-align: justify;">Examples</i><span class="Apple-style-span" style="text-align: justify;">)</span></li>
</ul>
</div>
<ul>
</ul>
<div>
<div style="text-align: justify;">
<div style="text-align: left;">
<br /></div>
</div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
Benefits:</div>
</div>
<div style="text-align: left;">
</div>
<ul>
<li><i style="text-align: justify;">Examples </i>&amp; <i style="text-align: justify;">Scenario </i><span class="Apple-style-span" style="text-align: justify;">layers clearly communicate the specification to Anybody (Customers could even modify it themselves)</span></li>
<li><i style="text-align: justify;">Steps </i>layer is actually a DSL (Domain-Specific Language) of the application. Exploring it creates a common domain-based language for Team Members and Customers.&nbsp;Further, it allows to execute the same set of tests via different interfaces implemented in the <i style="text-align: justify;">Glue </i><span class="Apple-style-span" style="text-align: justify;">layer</span></li>
<li><i style="text-align: justify;">Glue </i>layer drives us to create testeable classes and methods in the <i style="text-align: justify;">Application</i></li>
<li>Turns test (a.k.a. specification) writing into a creative and useful activity</li>
</ul>
<br />
<ul>
</ul>
<div>
<div style="text-align: justify;">
<div style="text-align: left;">
<br /></div>
</div>
</div>
<div>
<div style="text-align: justify;">
<div style="text-align: left;">
<b>Sample application driven by Robot Framework</b></div>
</div>
</div>
<div>
<div style="text-align: justify;">
<div style="text-align: left;">
<br /></div>
</div>
</div>
<div>
<div style="text-align: justify;">
<div style="text-align: left;">
Source code is available under:&nbsp;<a href="https://github.com/unclejamal/CashDispenser">https://github.com/unclejamal/CashDispenser</a></div>
</div>
</div>
<div>
<div style="text-align: justify;">
<div style="text-align: left;">
Prerequisites:&nbsp;Java 1.6,&nbsp;<a href="http://maven.apache.org/">Maven 3.x</a>, <a href="http://code.google.com/p/robotframework">Robot Framework 2.6+</a>&nbsp;(this is the setup I tested it with)</div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
<br /></div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
Building:</div>
<blockquote>
<pre>mvn clean install
</pre>
</blockquote>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
Testing
</div>
<blockquote>
<pre>cd atdd/cashdispenser-robot/target/
test.bat
</pre>
</blockquote>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
<br />
<div>
Test logs will be created in:</div>
<blockquote style="text-align: justify;">
<pre>atdd/cashdispenser-robot/target/output
</pre>
</blockquote>
<br />
<br /></div>
</div>
</div>
<div>
<div style="text-align: justify;">
<div style="text-align: left;">
<b>Nice-to-haves and what-nots</b></div>
</div>
</div>
<div>
<div style="text-align: justify;">
<div style="text-align: left;">
<br /></div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
In Java EE it would be nice to create two Glue layer implementations. First, that manipulates directly Java classes and uses test doubles to be separated from external services (this could be run after every single build). Second, that uses Jython to execute EJB public methods directly in the container (this is much slower, but permits a more end-to-end testing).</div>
</div>
</div>
<div>
<ul>
</ul>
<div style="text-align: justify;">
<div style="text-align: left;">
<br /></div>
</div>
<div style="text-align: justify;">
<div style="text-align: left;">
Finally, to see a hands-on example of BDD with Cucumber and Ruby, I strongly recommend watching&nbsp;Matt Wynne's podcast&nbsp;<a href="http://skillsmatter.com/podcast/agile-scrum/bdd-as-its-meant-to-be-done">"BDD as it's meant to be done"</a>.</div>
</div>
</div>
