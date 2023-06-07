Set-NodeFormatScript
--------------------




### Synopsis




---


### Description

Allows the definition of a custom node format



---


### Examples
#### EXAMPLE 1
```PowerShell
Set-NodeFormatScript -ScriptBlock {$_.ToLower()}
```



---


### Parameters
#### **ScriptBlock**

The Scriptblock used to process every node value






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ScriptBlock]`|false   |1       |false        |



#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them
#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.



---


### Notes
This can be used if different datasets are not consistent.



---


### Syntax
```PowerShell
Set-NodeFormatScript [[-ScriptBlock] <ScriptBlock>] [-WhatIf] [-Confirm] [<CommonParameters>]
```
