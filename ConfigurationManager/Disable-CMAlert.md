Disable-CMAlert
---------------




### Synopsis
Disable alerts



---


### Description

Use this cmdlet to disable one or more alerts in Configuration Manager.



Configuration Manager doesn't evaluate the condition for a disabled alert. It doesn't update a disabled alert, even if the state of the alert changes.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMAlert](Enable-CMAlert)



* [Get-CMAlert](Get-CMAlert)



* [Remove-CMAlert](Remove-CMAlert)



* [Set-CMAlert](Set-CMAlert)



* [Suspend-CMAlert](Suspend-CMAlert)





---


### Examples
#### Example 1: Disable an alert by using alert ID
```PowerShell
Disable-CMAlert -Id "16777218"
```

#### Example 2: Disable an alert by using alert object variable
```PowerShell
$AlertObj = Get-CMAlert -Id "16777221"
Disable-CMAlert -InputObject $AlertObj
```



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

Specify the ID of an alert to disable. You can get the ID of an alert by using the Get-CMAlert (Get-CMAlert.md)cmdlet.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **InputObject**

Specify an alert object to disable. To get this object, use the Get-CMAlert (Get-CMAlert.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Alert  |



#### **Name**

Specify the name of an alert to disable. You can get the name of an alert by using the Get-CMAlert (Get-CMAlert.md)cmdlet.






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
Disable-CMAlert [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Disable-CMAlert [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Disable-CMAlert [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
