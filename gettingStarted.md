Getting Started {#gettingStarted}
===============

This section provides a step-by-step tutorial for new DrJava developers
on setting up a build environment and making modifications to the code
base. It discusses much of the material only lightly, presenting just
the essential information required to get everything working properly.
Links are interspersed to more comprehensive treatment elsewhere.

Setting up Your Accounts
------------------------

### SourceForge

The DrJava project is hosted by SourceForge.net. We take advantage of
SourceForge\'s source control, Web space, bug tracking, and mailing list
features. Regardless of whether you will be committing code or not, we
recommend registering for a SourceForge user account to provide a point
of contact in the Tracker forums. If you will be a member of the DrJava
development team, the project administrators will add your account to
the project to allow you to commit code and respond to bugs and feature
requests.

-   If you don\'t already have a SourceForge user account, go to
    <http://sourceforge.net> and click on \"Create Account\"; follow the
    directions until your account is set up and you can log in to the
    site.

-   Visit the [DrJava project
    page](http://sourceforge.net/projects/drjava). The \"Tracker\" and
    \"Code\" sections (you made need to click on \"More\" first) are
    particularly relevant. You should also follow the \"Mailing Lists\"
    link and consider subscribing to one of the mailing lists.
    `drjava-hackers` is a high-traffic list containing all initial bug
    and feature request posts; `drjava-users` is generally limited to
    messages announcing new development and stable application releases.

-   If you are a member of the Rice DrJava development team, ask a
    project administrator to add you as a project member.

### Java PLT Group at Rice

For Rice students wishing to work with the DrJava developer team, you
should also do the following:

-   Get a Computer Science Department Unix account, if you don\'t
    already have one. This account is distinct from the Owlnet account
    given to all undergraduates, and will allow you to login and develop
    in the PLT computer lab. You can pick up an application from the
    department secretaries; have it signed by Corky Cartwright.

-   Subscribe to the `drjava` mailing list. You can do so here:
    <https://mailman.rice.edu/mailman/listinfo/drjava-l>. This list is
    the main electronic forum for communication among the team members
    (like a course discussion board). Feel free to post your ideas or
    ask for help here.

Installing Essential Software
-----------------------------

You will need to have three programs properly installed and set up on
any system you intend to use for development. These are the Sun Java
Development Kit or OpenJDK (for compilation), a Subversion or Git client
(to access the source code repository), and Apache Ant (for scripted
building).

### Sun Java Development Kit {#installJDK}

If it\'s not already installed on your system, you can download the JDK
from [Sun\'s Web site](http://java.sun.com). You will need to have
installed the JDK version 8 (note the distinction on the download pages
between a Java *Runtime Environment*, which just contains the tools
needed to *run* Java programs, and a Java *Development Kit*, which
contains a compiler and other tools, in addition to the runtime
application).

You should set up your command-line environment so that you can access
the `java` and `javac` commands. See [Command-Line Environment
Settings](#environmentSettings) for details.

::: {.note}
::: {.title}
Rice Java PLT
:::

On the Rice Computer Science department network, various versions of the
JDK are installed at `/home/javaplt/java`, organized by platform (such
as `Linux-i686`) and then by version.
:::

::: {#osx-java .note}
::: {.title}
Mac OS X
:::

As of OS X 10.7 (2011) Java is no longer built into Mac OS X, so you\'ll
have to install it yourself. If you haven\'t done so already, you should
install the Xcode Tools, distributed on CD or DVD with the OS, and also
available from the [Apple Developer
Connection](http://developer.apple.com) (free membership is required).
To see what is currently installed, go to
`/System/Library/Frameworks/JavaVM.framework/Versions`.

To select which version of Java is used to launch applications and to
run command-line tools, run
`/Applications/Utilities/Java/Java Preferences`. There is no need to
manually adjust the `PATH` variable or manipulate symbolic links.

For more information on Java in OS X, see [Apple\'s Java development
page](http://developer.apple.com/java) and, specifically, [this
FAQ](http://developer.apple.com/java/faq/).
:::

### Version Control Client {#installSubversion}

The DrJava source code is stored on a SourceForge server using
Subversion, and on GitHub using Git. This allows changes to the sources
to be tracked and permits a number of developers to work on different
parts of the code at the same time. In order to access the source
repository, you will need a Subversion client or a Git client. See the
[Subversion website](http://subversion.tigris.org/) or the [Git
website](https://git-scm.com/downloads) for links to a client for your
platform.

Your command-line path will need to be set up so that the `svn` or `git`
command is available. See [Command-Line Environment
Settings](#environmentSettings) for details.

::: {.note}
::: {.title}
Rice Java PLT
:::

On the Rice Computer Science department network, the Subversion client
is located at `/home/javaplt/packages/subversion-1.5.4/bin`.
:::

::: {.note}
::: {.title}
Mac OS X
:::

Subversion is installed with recent versions of Xcode Tools. See the
[previous note](#osx-java) for instructions on installing Xcode. After
this installation, you can find out if you have Subversion by typing
`svn --version` at the command line.
:::

### Apache Ant {#installAnt}

Ant is a build script interpreter MDASH loosely a Java- and XML-based
alternative to the `make` command on Unix systems. It can be downloaded
from [Apache\'s Web site](http://ant.apache.org). Decompress the package
and copy the `jakarta-ant-xxx` folder to a convenient location (such as
`/usr/local`, your home directory, or `C:\Program Files`).

Once installed, you should follow Apache\'s installation recommendations
for setting up your environment. See [Command-Line Environment
Settings](#environmentSettings) for details.

::: {.note}
::: {.title}
Rice Java PLT
:::

On the Rice Computer Science department network, Ant is available in the
`/home/javaplt/packages/apache-ant-1.x.x` directories.
:::

::: {.note}
::: {.title}
Mac OS X
:::

Ant is installed with the Xcode Tools. See the [previous
note](#osx-java) for details.
:::

### Command-Line Environment Settings {#environmentSettings}

Once you\'ve installed these programs on your system, you\'ll need to
ensure that your command-line environment is set up properly. Because
shells vary widely in the conventions they use, you may need to
familiarize yourself with the idiosyncrasies of your particular
platform.

::: {.note}
::: {.title}
\*nix
:::

On Unix and Unix-like systems, the environment variables can be set by
modifying a login script file. Assuming you are running a `bash` shell,
you can see how your environment is currently set up by typing `env`.
You can also use `which` to test the `PATH` variable MDASH for example,
`which
      ant` will print a full path to the `ant` executable if Ant is
correctly set up. It is important to check the current settings before
making changes.

To make changes to the default environment settings, edit (or create)
the `.bashrc` file in your home directory to contain the needed
declarations. (On some systems, such as Mac OS X or the Rice Owlnet
network, you should use the `.profile` file instead.) Under `bash`, an
environment variable is set with a command like the following:

::: {.informalexample}
`export
          ANT_HOME=/usr/local/ant`
:::

Note that path-like variables (such as `PATH` and `CLASSPATH`) should
use a colon (`:`) to delimit filenames. You can use a variable\'s value
at any time (both in a later declaration and at the command line) with
syntax like `$ANT_HOME`.

After making changes, you will need to open a new terminal window before
the settings will take effect.
:::

::: {.note}
::: {.title}
Microsoft Windows
:::

We recommend using [Ubuntu on
Windows](https://msdn.microsoft.com/en-us/commandline/wsl/about).

If you\'re using Cygwin (a Unix-like environment for Windows), many of
the \*nix instructions above are relevant. You *could*, for example,
define the environment variables in a `.bashrc` file. However, it\'s
probably best to use the system-wide Windows facilities (such as the
Environment Variables dialog box) whenever possible. One problem you
will encounter when using Cygwin is that Windows filenames and paths are
formatted differently from Cygwin filenames and paths. Generally, Java
applications (including Ant, with some exceptions) will only be able to
handle *Windows*-style paths. On the other hand, some Cygwin programs
expect Cygwin\'s Unix-like paths. To deal with this problem, you may
need to thoroughly familiarize yourself with the `cygpath` command,
which converts between the two formats.
:::

The following table summarizes the variables and corresponding values
that should be set up on your system:

  Variable      Value                                                                                                                                     Notes
  ------------- ----------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  `JAVA_HOME`   Location of the Java installation. The specified directory should have a `bin` subdirectory containing `java`, `javac`, `javadoc`, etc.   Required in order to locate the correct standard libraries when compiling. Rice CS: `/home/javaplt/java/Linux-i686/1.5`.
  `ANT_HOME`    Location of the Ant installation. The specified directory should contain the `bin` and `lib` subdirectories.                              The Ant command generally needs this in order to work correctly (although on some platforms Ant will work fine without it). Rice CS: `/home/javaplt/packages/ant`.
  `PATH`        For example, `$PATH:$JAVA_HOME/bin:$ANT_HOME/bin`.                                                                                        You will want the `ant` command on your path, as it will be used often. The Ant script requires that `java`, `javac`, and `svn` be available from the command line. You may want to explore the current settings before you make any modifications. Note the use of previously-declared environment variables in this example. Also keep in mind that the *first* matching location for a command in the path will shadow all later matches.

Accessing and Modifying the Source Code {#basicTutorial}
---------------------------------------

Now that your development system is ready, you can get to work! These
instructions will demonstrate some of the typical tasks you\'ll want to
accomplish in browsing, building, and modifying the DrJava sources.

### Downloading the Sources

You can use Subversion or Git to get a copy of the DrJava source code.
In Subversion terminology, downloading a fresh copy is (usually)
synonymous with \"checking out\" the code; the corresponding operation
with Git is \"cloning\" the repository. You can download the sources
with the following commands:

::: {.informalexample}
`$ svn co
        https://drjava.svn.sourceforge.net/svnroot/drjava/trunk/drjava`
:::

::: {.informalexample}
`$ git clone
        https://github.com/DrJavaAtRice/drjava.git`
:::

A `drjava` directory will be created in your working directory.
Subversion will output the name of each file it downloads, while Git
will give you progress reports along the way.

Note that the above Subversion command only checks out *part* of the
DrJava sources. The sources are divided into independent modules, each a
subdirectory of `trunk`. Each module can be built, tested, and modified
without the others. You can check out a different directory by simply
modifying the URL given to Subversion. Git works on a different model,
and as such cannot clone only part of a repository; the above Git
command will include all of the sources.

::: {.warning}
While it is possible to check out the entire
`https://drjava.svn.sourceforge.net/svnroot/drjava` directory, it is not
necessary. This top-level directory contains dozens of copies of the
sources, including snapshots at various stages of development. If you
download this directory, it will take a lot of time and disk space.
:::

The full list of `trunk`\'s subdirectories includes:

`drjava`

:   The main application, containing the bulk of the code. Building this
    module will create the DrJava application.

`dynamicjava`

:   The DynamicJava interpreter, which implements the functionality
    behind the Interactions Pane.

`javalanglevels`

:   A Java preprocessor used to provide the Language Levels facility.

`plt`

:   General-purpose utility classes, including things that are
    \"missing\" from the Java API like predicates and tuples.

`platform`

:   A collection of platform-dependent code, such as the concrete
    compiler interfaces and special OS-specific GUI setup instructions.

`docs`

:   The project documentation, including this document and end-user help
    files.

`eclipse`

:   A wrapper for the interactions pane that allows it to be run as a
    plug-in to the Eclipse IDE.

`jedit`

:   A similar wrapper for the interactions pane in the JEdit IDE.

`misc`

:   Files that don\'t belong in a specific module.

You may find it helpful to streamline the check-out process by creating
an alias or a script file for the check-out command.

### Building the Sources

In the `drjava` directory, you will find the file `build.xml`. This is
the module\'s Ant script, containing instructions that automate a
variety of development tasks. While in the `drjava` directory, enter:

::: {.informalexample}
`ant
        help`
:::

or just

::: {.informalexample}
`ant`
:::

The name `help` refers to an Ant target. Different targets can be used
to accomplish different tasks, and they are often set up to recognize
dependencies. For example, the `test` target recognizes its dependency
on the `compile` target; when you ask Ant to run the tests, it will
automatically compile them first. In this particular example, the `help`
target (which is set up as the default when none is specified) simply
prints a message about the script and the environment settings it
expects. If an error occurs here, Ant may not be properly set up.

Second, enter the following command:

::: {.informalexample}
`ant
        -p`
:::

You will see a list of all the documented targets in the project. Note
that, due to the dependencies between targets, the `build` target will
run `generate-source`, `compile`, `test`, and `jar`. That is, it will do
everything required to build and test a new application. Try it out:

::: {.informalexample}
`ant
        build`
:::

The process will take awhile. Ant will generally log each action it
takes to the console; you should make sure you can follow what\'s going
on. Here\'s a summary of the major steps:

-   **`generate-source`.**

    Performs any necessary preprocessing before the Java compiler is
    invoked. For example, a `Version.java` file is created so that a
    unique version number for this build will be accessible to the code
    (in particular, the DrJava application\'s About dialog box).

-   **`do-compile`.**

    Invokes the `javac` compiler (the specific version used depends on
    your command path). Generated class files will be placed in a new
    `classes` directory, with the subdirectories `base` and `test` for
    standard and test classes, respectively. Any compiler errors or
    warnings will be printed to the console. Where warnings are
    expected, they will be tagged in the code with a `@SuppressWarnings`
    annotation. Thus, any warnings you see during compilation highlight
    a problem that should be addressed.

-   **`unjar-libs`.**

    Expands the `*.jar` files in the `lib` directory into `classes/lib`.
    These library classes will be bundled with the finished product.

-   **`test`.**

    Runs the JUnit tests in `classes/test` (the specific version of
    `java` used depends on your command path). This will constitute the
    bulk of the build time. A summary of the running time for each test
    will be logged, and if a failure occurs, testing will halt
    immediately.

-   **`jar`.**

    Creates the `drjava.jar` file. This is the executable application.
    It will contain a `MANIFEST.MF` file listing the build\'s unique
    version number and your user name.

Now that you\'ve built the application, you can run it with the
following command:

::: {.informalexample}
`java -jar
        drjava.jar`
:::

You can also run the application in some systems by double-clicking on
the `drjava.jar` file. And the Ant script includes a variety of `run`
commands that act as shortcuts: `ant run-jar`, for example, will
compile, build a jar file, and run the application with assertions and
error logging turned on.

::: {.note}
::: {.title}
Mac OS X
:::

When you run the `drjava.jar` file, the DrJava GUI may not look quite
right. This is because the official OS X application release wraps the
jar file in some additional packaging and settings. However, all the
essential functionality should still be there in your unofficial
version.
:::

### Modifying the Sources

Once you\'ve got a fresh copy of the sources and verified that they will
build correctly, you\'re ready to start making modifications. The source
files are stored in the `src` directory; you should be able to explore
and edit them in any IDE or text editor. IDEs will be able to interface
with the build script with various degrees of sophistication. If the IDE
you use does not support Ant scripts (or you\'d rather not bother with
making it work properly), you can either do most of your building and
testing from the command line, or do your \"casual\" development in the
IDE, and just run the scripts when you are ready to commit a change. In
the latter case, you\'ll want to keep a few things in mind:

-   It\'s best to consider the contents of the `drjava` directory
    transient MDASH you will want to occasionally delete the directory
    completely and start from a fresh checkout. Thus, IDE-specific files
    like project descriptions are better stored somewhere else (unless
    you don\'t mind recreating them).

-   By default, the `javac` compiler places the `*.class` files it
    generates in the same location as their sources. That approach
    clutters up the `src` directory significantly, and should be
    avoided. You should also avoid putting the compiled classes in one
    of the Ant script\'s target locations (such as `classes/base`), as
    that might lead to confusing behavior when you invoke the script
    later. The best option is to either create a `classes/ide-name`
    directory in which to place your classes, or just store the
    IDE-compiled classes somewhere else entirely.

-   Your IDE\'s classpath should contain all the jar files in the `lib`
    directory (but not the `lib/buildlib` directory, with the exception
    of `lib/buildlib/junit.jar`).

-   You\'ll need to invoke the `generate-source` Ant target before you
    attempt to compile in the IDE (that is, unless the files have
    already been generated). Otherwise, some sources will be missing and
    the compilation will fail. Some IDEs may also have trouble with
    these files occasionally disappearing and reappearing, so you might
    want to ensure that the sources are in a consistent state before
    opening or closing the IDE application.

If you\'re using Eclipse, see the [Eclipse section](#eclipse) for
instructions on setting up a project.

To get oriented and understand the program design, you may want to
browse the [System Architecture](#systemArchitecture) notes, along with
the javadocs from the latest release (available at
[drjava.org](http://drjava.org)). You can also generate your own
up-to-date copy of the javadocs by invoking the Ant `javadoc` target.
Before you make significant changes to the code, you should familiarize
yourself with the [Development Best Practices](#bestPractices) section
of this document.

Once you\'ve made some modifications, you\'ll probably want to try them
out. The Ant script offers a couple of ways to do this. First, you can
enter

::: {.informalexample}
`ant
        run`
:::

This will run the DrJava application located in the `classes/base`
directory. You can also run the JUnit tests. You can run a *specific*
test (rather than waiting for *all* of them to run) by typing

::: {.informalexample}
`ant
        -Dtest-spec=filterString
        test`
:::

All test classes in `classes/test` with paths matching \<filterString\>
will be run by JUnit.

### Submitting Your Changes

When you\'re ready to submit the changes you\'ve made to the Subversion
archive (in Subversion terminology, commit the changes), and assuming
you\'re a member of the DrJava SourceForge project, you can do so with
the Ant script. If you\'re a Git user you will have to `commit` and
`push` manually, or if you don\'t have write access to the repository,
submit a [pull
request.](https://help.github.com/articles/about-pull-requests/)

While the `svn` command could be invoked directly from the command line
(or some IDEs), using Ant is the preferred approach because it allows
you to ensure that your changes do not break any functionality or
conflict with other changes that have been made by other developers
concurrently. The Ant script will run a fresh compile and all tests
before committing your changes.

If this is the first time you\'ve committed a change on your current
system, you will need to perform a manual commit in order to check your
authentication. You can do this by checking out the
`https://drjava.svn.sourceforge.net/svnroot/drjava/trunk/misc/authenticate`
directory and following the instructions in
`authenticate/authenticate.txt`. When you commit, you will be prompted
for a password (if the username is incorrect, just hit Enter and you
will be prompted for a username as well). \[TODO: Improve this process,
if possible. It would be nice if there were just an \"svn authenticate\"
command.\] That authentication information will be stored on your
system, and future commits will not require you to reenter your
password.

After your system is set up for automatic authentication, you can
perform a commit with the following:

::: {.informalexample}
`ant
        commit`
:::

The major steps in this process are enumerated below:

-   **`clean-intermediate`.**

    Removes all intermediate build products MDASH that is, files that
    didn\'t come from the Subversion repository and that aren\'t
    finished products. This will include generated sources and the
    `classes` directory. Note that, typically, this target (or just
    `clean`) is also invoked directly as the need arises.

-   **`clean-products`.**

    Removes all final build products. This will include DrJava jar files
    and generated javadocs.

-   **`update`.**

    Downloads all new changes that have been made in the Subversion
    repository since you last checked out (or updated) your sources. The
    command will list all filenames that are being changed locally;
    after the update, the `status` Subversion command will display any
    discrepancies between the repository and your working copy. If there
    is a conflict in the update (you and someone else have both changed
    the same file, or perhaps specifically an overlapping part of the
    same file), Subversion will let you know and give you a chance to
    manually merge the changes. This target is also typically invoked
    directly as the need arises (and you should use it *often* to catch
    conflicts while they are still small).

-   **`build`.**

    The project is built from scratch, as described previously. This
    ensures that your submission is a valid, tested copy of the program.

-   **`clean-intermediate`.**

    To prevent extraneous messages when the commit takes place, the
    project is cleaned up once again.

-   **`commit`.**

    You are first prompted to enter a log message describing the changes
    you\'ve made. These are generally just one-line summaries. Keep in
    mind that your message will be read in the context of the entire
    project when, for example, someone wants to know what changes have
    been made to the application recently. If you need help in
    remembering what files you\'ve touched, look at the output of
    `update`, which ran just before the project was rebuilt. Next, each
    file you\'ve modified will be uploaded and the changes will be
    assigned a fresh revision number.
