---
title: "Log"
linkTitle: "Log"
weight: 1
---

This section contains the APIs related to logging. 

## Listen to `console.log` events

Listen to the `console.log` events and register callbacks to process the event.

{{< tabpane text=true langEqualsHeader=true >}}
{{< tab header="Java" >}}
{{< gh-codeblock path="examples/java/src/test/java/dev/selenium/bidirectional/log/LogInspectorTest.java#L40-55" >}}
{{< /tab >}}
{{< tab header="Ruby" >}}
{{< /tab >}}
{{< tab header="JavaScript" >}}
{{< gh-codeblock path="examples/javascript/test/bidirectional/logInspector.spec.js#L23-37" >}}
{{< /tab >}}
{{< tab header="Kotlin" >}}
{{< /tab >}}
{{< /tabpane >}}

## Listen to JS Exceptions

Listen to the JS Exceptions
and register callbacks to process the exception details.

{{< tabpane text=true langEqualsHeader=true >}}
{{< tab header="Java" >}}
{{< gh-codeblock path="examples/java/src/test/java/dev/selenium/bidirectional/log/LogInspectorTest.java#L79-90" >}}
{{< /tab >}}
{{< tab header="Ruby" >}}
{{< /tab >}}
{{< tab header="JavaScript" >}}
{{< gh-codeblock path="examples/javascript/test/bidirectional/logInspector.spec.js#L44-54" >}}
{{< /tab >}}
{{< tab header="Kotlin" >}}
{{< /tab >}}
{{< /tabpane >}}

## Listen to JS Logs

Listen to all JS logs at all levels and register callbacks to process the log.

{{< tabpane text=true langEqualsHeader=true >}}
{{< tab header="Java" >}}
{{< gh-codeblock path="examples/java/src/test/java/dev/selenium/bidirectional/log/LogInspectorTest.java#L61-73" >}}
{{< /tab >}}
{{< tab header="Ruby" >}}
{{< /tab >}}
{{< tab header="JavaScript" >}}
{{< /tab >}}
{{< tab header="Kotlin" >}}
{{< /tab >}}
{{< /tabpane >}}