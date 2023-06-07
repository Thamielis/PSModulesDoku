Enable-CMAlert
--------------




### Synopsis
Enables Configuration Manager alerts.



---


### Description

The Enable-CMAlert cmdlet enables one or more Configuration Manager alerts.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAlert](Get-CMAlert)



* [Remove-CMAlert](Remove-CMAlert)



* [Set-CMAlert](Set-CMAlert)



* [Suspend-CMAlert](Suspend-CMAlert)



* [Disable-CMAlert](Disable-CMAlert)





---


### Examples
#### Example 1: Enable an alert by using alert ID
```PowerShell
PS XYZ:\>Enable-CMAlert -Id "16777223"
```
This command enables an alert that has the ID 16777223.
#### Example 2: Enable an alert by using an alert object variable
```PowerShell
PS XYZ:\> $AlertObj = Get-CMAlert -Id "16777218"
PS XYZ:\> Enable-CMAlert -InputObject $AlertObj
```
The first command gets the alert object that has the ID 16777218, and then stores it in the $AlertObj variable.


The second command enables the alert stored in the $AlertObj variable.


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



#### **Id**

Specifies an alert ID. You can obtain the ID of an alert by using the Get-CMAlert (Get-CMAlert.md)cmdlet.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **InputObject**

Specifies a CMAlert object. To obtain a CMAlert object, use Get-CMAlert .






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Alert  |



#### **Name**

Specifies an alert name. You can obtain the name of an alert by using Get-CMAlert .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Enable-CMAlert [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Enable-CMAlert [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Enable-CMAlert [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
