Chart and Graph Library for Android
====================================

<h2>What is GraphView</h2>
GraphView is a library for Android to programmatically create flexible and nice-looking diagramms. It is easy to understand, to integrate and to customize it.
At the moment there are two different types:
<ul>
<li>Line Charts</li>
<li>Bar Charts</li>
</ul>

Tested on Android 1.6, 2.2, 2.3 and 3.0 (honeycomb, tablet), 4.0.

<img src="https://github.com/jjoe64/GraphView/raw/master/GVLine.jpg" height="200" />
<img src="https://github.com/jjoe64/GraphView/raw/master/GVBar.png" height="200" />
<img src="http://3.bp.blogspot.com/-BkLSSJSeCt8/TkD4xpeRyGI/AAAAAAAAA6M/sVC_1s_Bf-0/s1600/multi2.png" height="200" />

<h2>Features</h2>

* Two chart types
Line Chart and Bar Chart.
* Draw multiple series of data
Let the diagram show more that one series in a graph. You can set a color and a description for every series.
* Show legend
A legend can be displayed inline the chart. You can set the width and the vertical align (top, middle, bottom).
* Custom labels
The labels for the x- and y-axis are generated automatically. But you can set your own labels, Strings are possible.
* Handle incomplete data
It's possible to give the data in different frequency.
* Viewport
You can limit the viewport so that only a part of the data will be displayed.
* Scrolling
You can scroll with a finger touch move gesture.
* Scaling / Zooming
Since Android 2.3! With two-fingers touch scale gesture (Multi-touch), the viewport can be changed.
* Background (line graph)
Optionally draws a light background under the diagram stroke.
* Manual Y axis limits
* Realtime Graph (Live)
* And more

<h2>How to use</h2>
<a href="http://android-graphview.org">View GraphView page <br/> http://android-graphview.org</a>

<h2>Important</h2>
To show you how to integrate the library into an existing project see the GraphView-Demos project!
See GraphView-Demos for examples.
<a href="https://github.com/jjoe64/GraphView-Demos">https://github.com/jjoe64/GraphView-Demos<br/>
<a href="http://android-graphview.org">View GraphView page http://android-graphview.org</a>

How to create a new version for maven repo
--------------------------------------------
create sources.jar
- $ jar cvf sources.jar src

create java doc jar
- $ mkdir javadoc
- $ javadoc -d javadoc -sourcepath src/main/java/ -subpackages com.jjoe64
- $ jar cvf javadoc.jar javadoc

change version in gradle.properties

uncomment part for publishing in build.gradle

(once) create a gpg file
- gpg --gen-key

(once) publish key
- gpg --send-keys D8C3B041
and/or here as ascii
- gpg --export -a D8C3B041
- http://keyserver.ubuntu.com:11371/

=> needs some time

hardcode user/pwd of nexus account in maven_push.gradle

run gradle task uploadArchives
-  ./gradlew --rerun-tasks uploadArchives
- enter gpg info (id:D8C3B041 / path: /Users/jonas/.gnupg/secring.gpg / PWD)

open https://oss.sonatype.org

login

Staging Repositiories

search: jjoe64

Close entry

Refresh/Wait

Release entry

Wait some days

How to create a new .jar file
--------------------------------
run this gradle task
- ./gradlew --rerun-tasks clearJar makeJar
copy myCompiledLibrary.jar from build/outputs/ to public/GraphView-x.x.x.jar

