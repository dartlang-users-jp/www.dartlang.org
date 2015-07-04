---
layout: default
title: "dartanalyzer: The Static Analyzer"
short-title: "dartanalyzer"
description: "The Dart tool for analyzing your Dart source from the command line."
has-permalinks: false
---

{% include toc.html %}
{% include breadcrumbs.html %}

# {{ page.title }}

You can use the *dartanalyzer* tool (`bin/dartanalyzer`) to statically
analyze your code at the command line, checking for errors and warnings
that are specified in the [Dart Language Specification](/docs/spec/).
DartPad, code editors, and IDEs such as WebStorm
use the same analysis engine that dartanalyzer uses.

## Basic usage

Run the analyzer from the top directory of the package.
Here’s an example of testing a Dart file.

{% prettify sh %}
dartanalyzer bin/test.dart
{% endprettify %}

As the following table shows,
the exit code of dartanalyzer tells you whether the code
passed analysis.

|-----------+----------------------------------------
| Exit code | Description
|-----------+----------------------------------------
| 0         | No issues found
| 1         | Hints found (but no warnings or errors)
| 2         | Warnings found
| 3         | Errors found
{:.table .table-striped}


## Options

You can use the following command-line options with dartanalyzer:

{% comment %}
{NOTE:
I'm still not documenting --perf. It's displayed by --help but seems of
limited use to most developers. I'm also not documenting the following,
which I got from sdk/bin/dartanalyzer or pkg/analyzer/lib/options.dart
but aren't displayed by help: -batch|--batch|-b (though -b doesn't seem
to be treated specially by the script), --ignore-unrecognized-flags
(doesn't seem to change the output), --fatal-warnings, --warnings (only
for SDK developers?), --show-sdk-warnings (deprecated)}
{% endcomment %}

`--dart-sdk=`
: Specify the directory that contains the Dart SDK.

`-p` *or* `--package-root=`
: **Deprecated.** Specify the directory to search for any libraries that are
  imported using `package:`.

`--package-warnings`
: Show warnings not only for code in the specified .dart file and
  others in its library, but also for libraries imported with
  `package:`.

`--format=machine`
: Produce output in a format suitable for parsing.

`--no-hints`
: Don't show hints for improving the code.

`--version`
: Show the analyzer version.

`-h` *or* `--help`
: Show all the command-line options.

