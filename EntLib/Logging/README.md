# Summary
This Enterprise Library is used to show examples of logging to Azure Application Insights from Power Apps. Below you will find further documentation including sample code, queries and alerts to assist.


# Sample Code

Sending an informational trace message

```
//Button Press
Trace(Self.Text & " pressed", TraceSeverity.Information, {
    Timestamp: Now(),
    ParentX: Parent.X,
    ParentY: Parent.Y,
    Id: "Button2",
    Tooltip: Self.Tooltip,
    Align: Self.Align,
    AlignInContainer: Self.AlignInContainer,
    Italiced: Self.Italic,
    X: Self.X,
    Y: Self.Y,
    ContentLanguage: Self.ContentLanguage,
    Height: Self.Height,
    Width: Self.Width,
    GlobalProperties: GlobalProperties.traceProperties
});
```

Sending an error trace message

```
IfError(1/0, Notify("Notify user"); Trace("Error occured on " + Self.Text + " OnSelect", TraceSeverity.Error, {
    Timestamp: Now(),
    Error: FirstError,
    ParentX: Parent.X,
    ParentY: Parent.Y,
    Id: "Button2",
    Tooltip: Self.Tooltip,
    Align: Self.Align,
    AlignInContainer: Self.AlignInContainer,
    Italiced: Self.Italic,
    X: Self.X,
    Y: Self.Y,
    ContentLanguage: Self.ContentLanguage,
    Height: Self.Height,
    Width: Self.Width,
    GlobalProperties: GlobalProperties.traceProperties
}));
```
