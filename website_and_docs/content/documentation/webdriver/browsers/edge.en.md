---
title: "Edge specific functionality"
linkTitle: "Edge"
weight: 5
description: >-
    These are capabilities and features specific to Microsoft Edge browsers.
---

Microsoft Edge is implemented with Chromium, with the earliest supported version of v79. Similar to Chrome,
the major version number of edgedriver must match the major version of the Edge browser.

All capabilities and options found on the [Chrome page]({{< ref "chrome.md" >}}) work for Edge as well.

## Options

Starting an Edge session with basic defined options looks like this:

{{< tabpane text=true langEqualsHeader=true >}}
{{< tab header="Java" >}}
{{< gh-codeblock path="/examples/java/src/test/java/dev/selenium/browsers/EdgeTest.java#L18-L19" >}}
{{< /tab >}}
{{% tab header="Python" %}}
{{< gh-codeblock path="/examples/python/tests/browsers/test_edge.py#L6-L7" >}}
{{% /tab %}}
{{< tab header="CSharp" >}}
{{< gh-codeblock path="/examples/dotnet/SeleniumDocs/Browsers/EdgeTest.cs#L12-L13" >}}
{{< /tab >}}
{{< tab header="Ruby" >}}
{{< gh-codeblock path="/examples/ruby/spec/browsers/edge_spec.rb#L9-L10" >}}
{{< /tab >}}
{{< tab header="JavaScript" >}}
{{< gh-codeblock path="/examples/javascript/test/getting_started/openEdgeTest.spec.js#L11-L15">}}
{{< /tab >}}
{{< tab header="Kotlin" >}}
{{< badge-code >}}
{{< /tab >}}
{{< /tabpane >}}

### Arguments

The `args` parameter is for a list of [Command Line Switches](https://peter.sh/experiments/chromium-command-line-switches/)
used when starting the browser.
Commonly used args include `--start-maximized` and `--headless=new`

Add an argument to options:

{{< tabpane text=true langEqualsHeader=true >}}
{{< tab header="Java" >}}
{{< gh-codeblock path="/examples/java/src/test/java/dev/selenium/browsers/EdgeTest.java#L24-L26" >}}
{{< /tab >}}
{{% tab header="Python" %}}
{{< gh-codeblock path="/examples/python/tests/browsers/test_edge.py#L12-L13" >}}
{{% /tab %}}
{{< tab header="CSharp" >}}
{{< gh-codeblock path="/examples/dotnet/SeleniumDocs/Browsers/EdgeTest.cs#L20-L21" >}}
{{< /tab >}}
{{< tab header="Ruby" >}}
{{< gh-codeblock path="/examples/ruby/spec/browsers/edge_spec.rb#L14-L15" >}}
{{< /tab >}}
{{< tab header="JavaScript" >}}
{{< badge-code >}}
{{< /tab >}}
{{< tab header="Kotlin" >}}
{{< badge-code >}}
{{< /tab >}}
{{< /tabpane >}}

## Internet Explorer Compatibility Mode

Microsoft Edge can be driven in "Internet Explorer Compatibility Mode", which uses
the Internet Explorer Driver classes in conjunction with Microsoft Edge.
Read the [Internet Explorer page]({{< ref "internet_explorer.md" >}}) for more details.
