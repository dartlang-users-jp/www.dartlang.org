---
layout: default
title: "Dart Tools"
description: "The tools that support the Dart language."
has-permalinks: false
---


# {{ page.title }}

A variety of tools are available for download,
once you're ready to move beyond
<a href="https://dartpad.dartlang.org"
   target="_blank">DartPad</a>.

---

<a name="tools"></a>
<h2>SDK and Dartium</h2>

All development requires the Dart SDK.
Dartium is optional but helpful for developing web apps.

<br>

<div class="row">
  <div class="col-md-6">
    <div class="media">
        <img class="pull-left media-object"
             src="images/dart-logo-48.png"
             alt="Dart logo">
      <div class="media-body">
        <a href="sdk/"><b>SDK</b></a>
      </div>
    </div>
  </div>

  <div class="col-md-6">
    <div class="media">
        <img class="pull-left media-object"
             src="images/dartium-logo-48.jpg"
             alt="Dart logo" />
      <div class="media-body">
        <a href="dartium/"><b>Dartium</b></a>
      </div>
    </div>
  </div>
</div>

---

<a name="ides"></a>
<h2>IDEs</h2>

If you don't already have a favorite IDE,
we recommend WebStorm,
which comes with Dart support.
You can also use a plugin to add Dart support to other JetBrains IDEs
and to Eclipse.

<br>

<div class="row">
  <div class="col-md-4">
    <div class="media">
        <img class="pull-left media-object"
             src="images/webstorm.png"
             alt="WebStorm logo">
      <div class="media-body">
        <a href="webstorm/"><b>WebStorm</b></a>
      </div>
    </div>
  </div>

  <div class="col-md-4">
    <div class="media">
        <img class="pull-left media-object"
             src="images/IntellIJ-IDEA.png"
             alt="IntelliJ logo">
      <div class="media-body">
        <a href="jetbrains-plugin/"><b>IntelliJ IDEA<br>
          (and other JetBrains IDEs)</b></a>
      </div>
    </div>
  </div>

  <div class="col-md-4">
    <div class="media">
        <img class="pull-left media-object"
             src="images/eclipse.png"
             alt="Eclipse logo">
      <div class="media-body">
        <a href="eclipse-plugin/"><b>Eclipse</b></a>
      </div>
    </div>
  </div>
</div>
---

<a name="plugins"></a>
<h2>Editors</h2>

If you prefer using a text editor,
try one of these Dart plugins
(which are unsupported and available as open source).

<br>

<div class="row">
  <div class="col-md-4">
    <div class="media">
        <img class="pull-left media-object"
             src="images/sublime.png"
             alt="Sublime logo">
      <div class="media-body">
         <a href="https://github.com/dart-lang/dart-sublime-bundle#readme"><b>Sublime Text 3</b></a>
      </div>
    </div>
  </div>

  <div class="col-md-4">
    <div class="media">
        <img class="pull-left media-object"
             src="images/emacs.png"
             alt="Emacs logo">
      <div class="media-body">
        <a href="https://github.com/nex3/dart-mode"><b>Emacs</b></a>
      </div>
    </div>
  </div>

  <div class="col-md-4">
    <div class="media">
        <img class="pull-left media-object"
             src="images/vim.png"
             alt="Vim logo">
      <div class="media-body">
        <a href="https://github.com/dart-lang/dart-vim-plugin"><b>Vim</b></a>
      </div>
    </div>
  </div>
</div>


---

<a name="other-tools"></a>
<h2>Command-line tools and Observatory</h2>

These tools are in the [Dart SDK](/tools/sdk).

<div class="row">
  <div class="col-md-4">
    <dt> <a href="/tools/dart-vm">dart</a> </dt>
      <dd>Standalone VM </dd>
    <dt> <a href="/tools/dart2js/">dart2js</a> </dt>
      <dd>Dart-to-JavaScript compiler </dd>
  </div>
  <div class="col-md-4">
    <dt> <a href="/tools/analyzer">dartanalyzer</a> </dt>
      <dd>Static analyzer </dd>
    <dt> <a href="/tools/dartdocgen/">dartdocgen</a> </dt>
      <dd>API documentation generator </dd>
    <dt> <a href="/tools/observatory/">Observatory</a> </dt>
      <dd>Profiler for Dart apps</dd>
  </div>
  <div class="col-md-4">
    <dt> <a href="/tools/dartfmt/">dartfmt</a> </dt>
      <dd>Code formatter</dd>
    <dt> <a href="/tools/pub/">pub</a> </dt>
      <dd>Package and asset manager </dd>
  </div>
</div>

---

This is not an exhaustive list of tools available
for Dart development and does not reflect many fine tools developed
by the Dart community.

Also see the <a href="/tools/faq.html">Tools FAQ</a>.

---

<a name="dump-info-visualizer"></a>
<h2>Curious about your generated JavaScript?</h2>
<p>
If you are compiling your Dart code to JavaScript with dart2js, the Dump-Info
Visualizer can give you insight into what is going on behind the scenes.
Use it to analyze the generated code and see why that code is included in
your build.

<div class="media">
      <img class="pull-left media-object"
         src="images/dump-info-viewer.png"
         alt="sample Dump-info visualizer output">
  <div class="media-body">
    <a href="https://github.com/dart-lang/dump-info-visualizer"><b>Dump-Info Visualizer</b></a>
  </div>
</div>
