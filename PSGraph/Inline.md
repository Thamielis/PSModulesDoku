Inline
------




### Synopsis




---


### Description

Allows you to write native DOT format commands inline with proper indention



---


### Examples
#### EXAMPLE 1
```PowerShell
graph g {
    inline 'node [shape="rect";]'
}
```



---


### Parameters
#### **InlineCommand**

The text to generate inline with the graph






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |1       |false        |





---


### Notes
You can just place a string in the graph, but it will not indent correctly. So all this does is give you correct indents.



---


### Syntax
```PowerShell
Inline [[-InlineCommand] <String[]>] [<CommonParameters>]
```
