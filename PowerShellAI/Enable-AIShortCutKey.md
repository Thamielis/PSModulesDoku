Enable-AIShortCutKey
--------------------




### Synopsis
Enable a shortcut key for getting completions



---


### Description

Enables a shortcut key for getting completions.

The -ShortcutKey can be customized.

If not in Visual Studio Code, the ShortcutKey will default to 'CTRL+G'
In Visual Studio Code, the ShortcutKey will default to 'ALT+G'



---


### Examples
#### EXAMPLE 1
```PowerShell
# Enables the shortcut key.  Outside of VSCode, CTRL+G.  Inside of VSCode, ALT+G.
Enable-AIShortCutKey
```

#### EXAMPLE 2
```PowerShell
Enable-AIShortCutKey -ShortcutKey "CTRL+ALT+P"
```



---


### Parameters
#### **ShortcutKey**

In Visual Studio Code, CTRL+G is "goto",
so we'll use ALT+G by default.
If we're not running in code, use CTRL+G by default






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |1       |false        |





---


### Syntax
```PowerShell
Enable-AIShortCutKey [[-ShortcutKey] <String>] [<CommonParameters>]
```
