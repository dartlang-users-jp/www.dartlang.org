---
layout: tutorial
title: "Get Started"
description: "Get Dart and run two Dart applications"
has-permalinks: true
tutorial:
  id: get-started
next: connect-dart-html/
next-title: "Connect Dart & HTML"
prev:
prev-title: "Home"
---

{% capture whats_the_point %}

* The Dart SDK has development tools and libraries.
* You can use Dart for web apps and command-line apps.
* Run Dart web apps directly in Dartium.
* Use an IDE (such as WebStorm) or code editor to create your app.
* Compile Dart apps to JavaScript for other browsers.
* All Dart apps have a main() function.
* Dart supports top-level functions.

{% endcapture %}

{% capture sample_links %}

This tutorial features two examples:

* hello_world
* simple

{% endcapture %}

{% capture content %}

<div class="tute-target-title">
<h1>{{page.title}}</h1>
<h3>Get Dart. Run two apps.</h3>
</div>

If you haven't yet written any Dart code, go
[build a pirate app in DartPad](/codelabs/darrrt/).
That code lab features DartPad, which lets you
write and run Dart apps in any browser
without downloading anything.

This tutorial gets you ready
to begin writing Dart apps in an editor or IDE.
Here you will download the Dart software and
create and run two small applications.

* [Download Dart and an IDE](#download-dart)
* [What did you get?](#what-did-you-get)
* [About Dart applications](#what-is-app)
* [Create a command-line app](#create-cmd-line)
* [Run a command-line app](#run-cmd-line)
* [Create a web app](#create-web-app)
* [Run a web app](#run-web-app)
* [About main() and other top-level functions](#top-level-functions)
* [About file naming conventions](#file-names)
* [Other resources](#other-resources)
* [What next?](#what-next)

##Download Dart and an IDE {#download-dart}

Once you are ready to move beyond DartPad and create Dart apps in
a real world environment, you need to download some software.

At the very least, you need the Dart SDK, which contains all of
the tools and libraries that you need for basic Dart development.
We also recommend that you download Dartium, which is useful for
web development. You may also want an IDE or code editor;
this tutorial uses WebStorm.

* [Get the Dart SDK](/downloads/)
* Recommended: [Get Dartium](/downloads/)
* Recommended: [Get WebStorm](/tools/webstorm/)


##What did you get? {#what-did-you-get}

When you download the **Dart SDK**, you get a directory
that contains tools (under `bin`) and libraries (under `lib`),
along with supporting files.
The location of the directory (we'll call it the _&lt;sdk-install-dir&gt;_)
depends on your platform and how you downloaded the SDK.

Under _&lt;sdk-install-dir&gt;_/lib are Dart libraries, such as dart:core,
dart:html, and dart:io, that define APIs useful to most apps.
The _&lt;sdk-install-dir&gt;_/bin directory contains several useful
command-line tools, such as the **pub** package manager,
the Dart-to-JavaScript compiler,
and the command-line version of the Dart VM.

When you download **Dartium**, you get a special build of the
Chromium web browser that has the Dart VM (virtual machine) embedded.
(While the app is referred to as _Dartium_, the executable
is actually named **Chromium**.)
You can run your apps directly in this browser,
or have your IDE or code editor do it for you,
thereby streamlining the build-test cycle.

**WebStorm** has a pre-installed Dart plugin,
but it requires a bit of configuration,
as we'll describe later.
If you prefer to use another IDE or code editor,
you might want to download and install a Dart plugin,
if available.
See the [tools page](/tools/) for a list of plugins.


##About Dart applications {#what-is-app}

There are two kinds of Dart applications:
command-line applications and web applications.
A command-line application is a standalone program
that you run in the Dart VM from the command line in a terminal window.
Web applications are hosted on a web page and run in a browser
(either directly in a browser that supports Dart
or by compiling to JavaScript).

A minimal Dart application has

* one Dart source file&mdash;a
  file with the .dart suffix that contains Dart code.
* one top-level main() function.
  This is the entry point for your application.
* a pubspec.yaml file containing the name of the app and (optionally)
  a description. For example:

{% prettify yaml %}
name: hello_world
description: A sample command-line application.
{% endprettify %}

###Pub package manager

The [`pub`](/tools/pub) tool allows you to manage Dart packages.
Pub also includes commands for creating, developing, and deploying
Dart applications. Behind the scenes, [`pub run`](/tools/pub/cmd/pub-run.html),
for example, uses the Dart VM tool to run a command-line application,
and [`pub build`](/tools/pub/cmd/pub-build.html) uses
the Dart-to-JavaScript compiler to convert a Dart web app to JavaScript.

Pub uses the metadata in the `pubspec.yaml` file to determine
your app's dependencies and any special setup that your app requires.
Pub assumes that the files and directories in a Dart application are
laid out in a particular way. The following diagram shows some of the
conventions used by pub. Not all of these directories are required.

<img class="scale-img-max" src="images/pub-directory-structure.png"
alt="Pub's directory structure including bin, lib, web and build directories,
and the pubspec file">

`bin`
: The main files for a command-line application. One of the
  files must include a top-level main() function.

`build`
: Created by `pub build` to contain the generated, deployable version
  of a Dart web app.

`lib`
: Additional code to be used by your command-line or web application.

`pubspec.yaml`
: The app's metadata, including information about which
  packages the app depends on and which versions of those
  packages are required.

`web`
: The main files for a web application, including HTML, Dart,
  and CSS files. One of the Dart files must include a top-level
  main() function.

You can invoke pub commands from the command line or from the WebStorm UI.

###Command-line applications

Dart command-line applications
run standalone from the command line,
independent of a web browser.
Command-line apps are often used
to provide server-side support to a web app,
but they can also be scripts.

The Dart VM runs Dart code directly without intermediate compilation.

<img class="scale-img-max" src="images/dartvm-cmd-line.png"
     alt="Run a command-line application without compilation">

###Web applications

Dart web applications run inside of a browser page.
In addition to a Dart file,
a web app requires an HTML file to host the app.
Often, a web app provides the client-side
user interface for a server.

The rest of this tutorial steps you through
creating and running first a command-line application
and then a web application.

##Create a command-line app {#create-cmd-line}

<ol>
<li markdown="1">
Launch WebStorm. This brings up a "Welcome to Webstorm" dialog.
</li>

<li markdown="1">
If this is the first time you have run WebStorm, you will
need to set the paths to Dartium and the SDK.
You can find the instructions at
[Configuring Dart support](/tools/webstorm/#configuring-dart-support).
</li>

<li markdown="1">
Choose **Create New Project**.
A dialog appears asking you to fill out a simple form.
</li>

<li markdown="1">
Select **Dart** from the list on the left.
</li>

<li markdown="1">
Replace the `untitled` portion of the string with `hello_world`.
This name is used for the app's directory name and package name.
By convention, these names are lowercase, with words
separated by underscores (`_`).
</li>

<li markdown="1">
Make sure that **Generate sample content** is checked.
</li>

<li markdown="1">
Select **Console Application** from the list.
</li>

<li markdown="1">
Click **Create**.
</li>
</ol>

WebStorm creates a `hello_world` directory for the application
and boilerplate files for a small command-line app.
It then runs `pub get` to download the packages that the app depends on.

<aside class="alert alert-info" markdown="1">
**If you don't have WebStorm:**
You can create the command-line app's files
using the **console-full** generator from
[Stagehand.](http://stagehand.pub/)
Then run `pub get`.
</aside>

Some of the files and directories in the hello_world application
include the following:

.pub
: Support files used by the pub tool. You can ignore this.

bin
: Contains the source files for the application.
  Expand `bin` to see `main.dart`, which is the main
  Dart file for this example.

pubspec.yaml
: Declares which packages your application needs.

pubspec.lock
: A generated file that specifies the version numbers
  of the packages on which the application depends.

lib
: Contains library code. Expand `lib` to see
  `hello_world.dart`, a library file with
  a simple calculate() method.

packages
: Contains code for the packages that your app uses.
  This code is fetched by the `pub get` command.

Double-clicking any filename displays the contents of that file
in the pane to the right.

The messages pane at the bottom contains the results of calling
`pub get`, which fetches the packages used by the app.

When executed, the program prints
"Hello world: 42!" to the standard output stream,
using the print() function provided by the dart:core library.
The functions and objects defined in the dart:core library
are automatically available to all Dart applications.

##Run a command-line app {#run-cmd-line}

In WebStorm, you can run the app in any of the following ways:

* Click the Run button
<img class="scale-img-max" src="images/run.png" width="16" height="16"
     alt="Run button"> in the upper right corner.
* Click the Run button to the left of the messages pane.
* Right-click main.dart in the files pane and select **Run 'main.dart'**
  from the pop-up menu.

WebStorm shows the output at the bottom in a pane titled
**Run main.dart**.

<aside class="alert alert-info" markdown="1">
**If you don't have WebStorm:**
You can run the app from the command line using
`pub run bin/main.dart`.
</aside>


##Create a web app {#create-web-app}

Now let's create a web application.

<ol>
<li markdown="1">
  Select **File** > **New Project** from the menu.
</li>

<li markdown="1">
Select **Dart** from the list on the left.
</li>

<li markdown="1">
Replace `untitled` with `simple` in the **Location** field.
</li>

<li markdown="1">
Make sure that **Generate sample content** is checked.
</li>

<li markdown="1">
Select **Uber Simple Web Application** from the list.
(It is at the bottom of the list&mdash;you may have to lengthen the dialog
 window to see it.)
</li>

<li markdown="1">
Click **Create**.
</li>
</ol>

WebStorm creates the directory and files needed for a basic
web application that prints "Your Dart app is running"
in the browser window.

<aside class="alert alert-info" markdown="1">
**If you don't have WebStorm:**
You can create the web app's files
using the **web-simple** generator from
[Stagehand.](http://stagehand.pub/)
</aside>

The top-level directory is named `simple`.
Expand `simple` in the left pane
to see the files. This is a client app, so expand the
`web` directory to see the client files.
The Dart source file that contains the main() function is
`web/main.dart`, and the `web/index.html` file hosts the app.
The `web/styles` directory contains the CSS styling for the app,
but you can ignore that for now.

The main() function in the simple app contains Dart code
that puts text on the browser page.
This code uses API defined in the dart:html library.

In the next tutorial,
you will build a mini app from scratch,
creating the Dart source, the HTML source,
and the CSS source yourself.

##Run a web app {#run-web-app}

In WebStorm, you can run the app in any of the following ways:

* Click the Run button
<img class="scale-img-max" src="images/run.png" width="16" height="16"
     alt="Run button"> in the upper right corner.
* Right-click index.html in the files pane and select **Run 'index.html'**
  from the pop-up menu.

WebStorm invokes Dartium (or, if you don't have Dartium,
your default browser) to display the simple app.
Behind the scenes, WebStorm uses `pub serve`,
which compiles the app to JavaScript
so that non-Dartium browsers can run it.
The browser loads the simple app's HTML file
and the embedded app,
which prints "Your Dart app is running" in the browser.

<aside class="alert alert-info" markdown="1">
**If you don't have WebStorm:**
Serve the app from the command line
by going to the app's top directory and running
`pub serve`.
To see the output, navigate to
[http://localhost:8080](http://localhost:8080)
in Dartium or any modern browser.
</aside>


##About main() and other top-level functions {#top-level-functions}

Dart lets you define _top-level_ functions,
that is, functions that are not encapsulated within a class or object.
All apps have at least one top-level function,
namely the main() function.

The two apps you've seen in this tutorial have other top-level functions.
The Hello World example calls print(),
a top-level function defined in dart:core.
And the simple app calls querySelector().text, a top-level function
defined in dart:html.

A function declaration
has two parts: a _signature_ and a _body_.

<img class="scale-img-max" src="images/function-parts.png"
     alt="Two parts of a function, the signature and the body"/>

The signature sets the function name,
the data type of its return value,
and the number and type of its input arguments.

<img class="scale-img-max" src="images/signature-parts.png"
     alt="The parts of a function signature"/>

The body is the code that defines the function's behavior.
It usually appears between curly braces ({_code_}).
If the body is a single expression, then you
can skip the braces and use the => shorthand:

{% prettify dart %}
double milesToKM(double miles) => miles/0.62;
{% endprettify %}

The milesToKM() function performs a simple arithmetic calculation
and returns the result.

This function takes a single argument.
Functions can take multiple arguments,
in which case the arguments are set apart by commas.

##About file naming conventions {#file-names}

When creating an application with WebStorm,
you are asked to provide an application name.
By convention, application names
(and thus, the related files and directories) are lowercase,
with words separated by underscores (`_`).

##Other resources

<ul>
  <li>
    The <a href="/tools/webstorm/">WebStorm</a> page
    provides more information about this tool.
  </li>
  <li>
    The <a href="/tools/pub/">pub</a> pages contain more information
    about Dart's package and asset manager.
  </li>
  <li>
    The <a href="/docs/">Programmer's Guide</a>
    points you to docs, articles,
    and other resources to help you as you create,
    test, and deploy Dart code.
  </li>
</ul>

##What next?

* Get the code for all of the Dart tutorials samples.
  <a href="https://github.com/dart-lang/dart-tutorials-samples/archive/master.zip">
  Download the ZIP file</a>, unzip it,
  and open `dart-tutorials-samples-master` in WebStorm.

* Go to the next tutorial,
  [Connect Dart & HTML](/docs/tutorials/connect-dart-html/),
  which steps you through writing a tiny web app from scratch.

{% endcapture %}

{% include tutorial.html %}
