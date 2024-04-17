**About DrJava**

* * *

DrJava is a lightweight development environment for writing Java programs. It is designed primarily for students, providing an intuitive interface and the ability to interactively evaluate Java code. It also includes powerful features for more advanced users. DrJava is available for free under the [BSD License](license.shtml), and it is under active development by the JavaPLT group at Rice University.

**Transition to Open JDK 8**

Effective Jan 1, 2019, Oracle changed the licensing terms for Java SE 8 which no longer allow free usage of the platform for commercial purposes. Even some non-commercial users of DrJava such as school districts who fear legal jeopardy under the new licensing terms can no longer use Oracle Java SE 8. Fortunately, there is a transparent open source alternative to Oracle Java SE 8, namely OpenJDK 8, but it is not distributed through the Oracle Java download site. There are several distributions of Open JDK 8 that are professionally supported by major corporations, most notably Amazon Corretto 8. In addition, Open JDK 8 is the standard version of Java 8 included in most Linux distributions such as Ubuntu. The latest beta release of DrJava works transparently with OpenJDK 8 and OpenJRE 8 on all platforms. In essence, any open distribution of Java 8 should suffice. Nevertheless, we strongly recommend installing the Amazon Corretto 8 distribution of Open JDK 8 available from the [Amazon Correcto download page](http://https://aws.amazon.com/corretto/) because this distribution appears to be the most comprehensive and best supported formulation of Open Java 8.

**Current Beta Release**

* * *

The current beta release for DrJava is drjava-beta-2019-220051 . This version is compatible with Java 8, which is the only supported version of "traditional" Java. Later versions of Java use a new package system and distribution format breaking compatibility with Java applications that access files in the underlying distribution. This release is only distributed as a jar file because it minimizes cross-platform compatibility issues. On Windows machines, the Amazon Corretto implementation modifies the registry so that clicking on a Java jar file runs the file on the Corretto Java 8 JVM. Mac users should download the DrJava jar file, open the Security and Privacy panel in the System Preferences app, and check the box stating that they want to open the DrJava jar file, even though is was produced a developer unknown to (unregistered with) Apple. Then the Jar file can be run using either the Oracle Java 8 or Amazon Corretto Java 8. A JRE distribution (which does not include a compiler) should suffice because the DrJava jar includes the compiler from the Java 8 OpenJDK.

([more download options](download.shtml))

  
**Filing Bug Reports or Feature Requests on SourceForge**

* * *

Note that you need to [log in with your SourceForge account](https://sourceforge.net/account/login.php) first before you can file a request. If you do not have a SourceForge account, please [register yourself at SourceForge](https://sourceforge.net/account/registration/). This measure was necessary to reduce the amount of spam we receive from automated "bots".

  

**Over Three Million Downloads of DrJava**

* * *

We are nearing the milestone of four million downloads of DrJava. There have been

3,879,430

  

downloads as of 13 Aug 2019. Thank you for making DrJava so successful!

([statistics by SourceForge](https://sourceforge.net/project/stats/detail.php?group_id=44253&ugn=drjava&type=prdownload&mode=alltime&file_id=0))

**News and Updates**

* * *

div#rssincl-box-98141 \*{ font-family: Arial, Helvetica, sans-serif; text-align:left; margin:0; padding:0; line-height:110%; clear:both; } div#rssincl-box-98141 { border:1px solid #808080; } div#rssincl-box-98141 div.rssincl-head { padding:5px; background-color: #CCCCFF; border-bottom:1px solid #808080; } div#rssincl-box-98141 div.rssincl-head p.rssincl-title, div#rssincl-box-98141 div.rssincl-head p.rssincl-title a { font-family: Arial, Helvetica, sans-serif; font-size: 15px; font-weight:bold; color: #FFFFFF; text-decoration:none; } div#rssincl-box-98141 div.rssincl-content {} div#rssincl-box-98141 div.rssincl-content div.rssincl-entry { padding:5px; background-color: #FFFFFF; border-bottom:1px solid #808080; } div#rssincl-box-98141 div.rssincl-content div.rssincl-last { border-bottom:none; } div#rssincl-box-98141 div.rssincl-content div.rssincl-entry p.rssincl-itemtitle { margin-bottom:6px; } div#rssincl-box-98141 div.rssincl-content div.rssincl-entry p.rssincl-itemtitle a { font-family: Arial, Helvetica, sans-serif; font-size: 13px; font-weight:bold; text-decoration:underline; color: #333333; } div#rssincl-box-98141 div.rssincl-content div.rssincl-entry div.rssincl-itemdesc, div#rssincl-box-98141 div.rssincl-content div.rssincl-entry div.rssincl-itemdesc \*{ font-family: Arial, Helvetica, sans-serif; font-size: 12px; color: #333333; } div#rssincl-box-98141 div.rssincl-content div.rssincl-entry div.rssincl-backlink { font-family: ; font-size: 10px; color: #333333; } div#rssincl-box-98141 div.rssincl-content div.rssincl-entry div.rssincl-backlink a { color: #333333; line-height:130%; text-decoration: none; } div#rssincl-box-98141 div.rssincl-content div.rssincl-entry div.rssincl-itemdesc img { margin: 5px; } div#rssincl-box-98141 div.rssincl-content div.rssincl-entry div.rssincl-clear { clear:both; }

DrJava News and Updates

[DrJava discussion](https://sourceforge.net/p/drjava/news/2014/08/drjava-/)

If we can muster the resources, we will replace he current DrJava interpreter (based on Dynamic Java, a European open source project that terminated in late 2001 \[see [](http://c2.com/cgi/wiki?DynamicJava)[http://c2.com/cgi/wiki?DynamicJava](http://c2.com/cgi/wiki?DynamicJava)\]) with the Java REPL interpreter (see [http://www.javarepl.com/console.html](http://www.javarepl.com/console.html)) for Java 8. This interpreter relies on incremental compilation to perform interpretation implying it can easily accommodate new language features in future versions of Java.

A similar interpreter is being bundled with Java in Java 9. Unfortunately, Java 9 will require drastic changes to DrJava because it completely re-organizes the library structure of Java. It is not clear whether we have the resources to create a DrJava for Java 9.

[DrJava Beta Release 20160913-225446](https://sourceforge.net/p/drjava/news/2016/09/drjava-beta-release-20160913-225446/)

Available for download at [http://drjava.org.](http://drjava.org.)

DrJava is a lightweight programming environment for Java designed to foster test-driven software development. It includes an intelligent program editor, an interactions pane for evaluating program text, a source level debugger, a unit testing tool, and a new code coverage tool.

In addition to bug fixes, this beta release includes two new features introduced since the last stable release:

1.  The new Toolbar button labeled "Coverage" runs all of your unit tests (just like the "Test" button) and determines the code coverage (branches and statements) of these unit tests using Jacoco code coverage tool. It generates and displays pages with links reporting the code coverage of your unit tests.
    
2.  In the "Edit preferences" menu, the Fonts pane includes two new options: "MenuBar Font" and "ToolBar Font". The MenuBar Font option also controls the font in tab labels in the Tabbed Pane (including "Interactions" and  
    "Find/Replace" among other tabs) below the Definitions window.
    

Note: Java 6 compatibility has been dropped. To use DrJava, you will need Java 7 or newer.

Bug fixes since the last stable release:

We have tried to fix some minor bugs some of which have been introduced in recent versions of DrJava. Please report bugs that you encounter using the SourceForge bug reporting and tracking system. We have very limited resources but we will try to address major bugs as quickly as possible and minor bugs that are easy to fix before the next release.

[DrJava discussion](https://sourceforge.net/p/drjava/news/2014/08/drjava-/)

When is Java 8 support in the Interactions pane expected?

[DrJava](https://sourceforge.net/p/drjava/news/2014/08/drjava-/)

[DrJava Stable Release 20130901-r5756](https://sourceforge.net/p/drjava/news/2013/09/drjava-stable-release-20130901-r5756/)

Available for download at [http://drjava.org](http://drjava.org) .

DrJava is a lightweight programming environment for Java designed to foster test-driven software development. It includes an intelligent program editor, an interactions pane for evaluating program text, a source level debugger, and a unit testing tool.

In addition to bug fixes, this stable release includes a number of new features introduced after the last stable release:

Note: Java 5 compatibility has been dropped. To use DrJava, you will need Java 6 or newer.

New features since the last stable release:  
\- DrJava is now compatible with Java 8 and perhaps with future editions of Java.

Bug fixes since the last stable release:  
\- DrJava correctly finds and labels Oracle JDK 7 compilers on Mac OS X.

NOTE: Newer releases of Mac OS X include a gatekeeper that will not run unlicensed applications like DrJava unless you explicitly open DrJava by "right" (control-key) clicking on the DrJava icon and executing the "Open" command. After you manually open DrJava once, Mac OS X remembers that it should be allowed to run and will open DrJava normally like other applications. Most open source applications like DrJava will not be licensed on Mac OS X because Apple charges a fee for this service.

[**RSS Widget for Website**](http://www.rssinclude.com/?utm_source=rssbox&utm_medium=link&utm_campaign=rsswidgetforwebsite)

* * *

[![YourKit Logo](images/yjp.gif)](http://www.yourkit.com/)

The DrJava Team thanks [YourKit, LLC](http://www.yourkit.com) for providing free licenses of the YourKit Java Profiler.

[![Hosted by SourceForge.net](http://sourceforge.net/sflogo.php?group_id=44253&type=1)](https://sourceforge.net/projects/drjava) DrJava has been partially funded by the [National Science Foundation](http://www.nsf.gov), the [Texas Advanced Technology Program](http://www.arpatp.com/), and [Sun Microsystems, Inc.](http://java.sun.com)
