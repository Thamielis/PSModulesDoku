Invoke-CMClientOperationSummarization
-------------------------------------




### Synopsis
Performs a Configuration Manager client operations summarization.



---


### Description

The Invoke-CMClientOperationSummarization cmdlet performs a Configuration Manager client operations summarization immediately, instead of waiting for the next scheduled summarization. This cmdlet does not change the regular schedule for summarizations.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Clear-CMClientOperation](Clear-CMClientOperation)



* [Remove-CMClientOperation](Remove-CMClientOperation)





---


### Examples
#### Example 1: Invoke summarization
```PowerShell
PS XYZ:\>Invoke-CMClientOperationSummarization
```
This command performs a client operations summarization immediately.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Invoke-CMClientOperationSummarization [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```