Set-CMAlert
-----------




### Synopsis
Changes properties of Configuration Manager alerts.



---


### Description

The Set-CMAlert cmdlet changes the properties of one or more Configuration Manager alerts.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMAlert](Enable-CMAlert)



* [Get-CMAlert](Get-CMAlert)



* [Remove-CMAlert](Remove-CMAlert)



* [Suspend-CMAlert](Suspend-CMAlert)



* [Disable-CMAlert](Disable-CMAlert)





---


### Examples
#### Example 1: Set alert properties
```PowerShell
PS XYZ:\> Set-CMAlert -Id "16777223" -Comments "Editing severity" -Severity 2
```
This command changes the values of the Comments and Severity properties for an alert that has the ID 16777223.
#### Example 2: Set alert properties by using alert object variable
```PowerShell
PS XYZ:\> $AlertObj = Get-CMAlert -Id "16777221"
PS XYZ:\> Set-CMAlert -InputObject $AlertObj -Comments "Updating alert"
```
The first command gets an alert object that has the ID 16777221, and then stores it in the $AlertObj variable.


The second command changes the Comments property of the alert stored in the $AlertObj variable.


---


### Parameters
#### **Comment**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |Comments|



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



#### **NewName**

Specifies a new name for the alert.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ParameterValue**








|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |named   |False        |ParameterValues|



#### **Severity**

Specifies the severity of an alert. The acceptable values for this parameter are:


* 1: Error


* 2: Warning


* 3: Informational



Valid Values:

* Error
* Warning
* Informational






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[Severities]`|false   |named   |False        |



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
Set-CMAlert [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-ParameterValue <String>] [-Severity {Error | Warning | Informational}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAlert [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-ParameterValue <String>] [-Severity {Error | Warning | Informational}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAlert [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-ParameterValue <String>] [-Severity {Error | Warning | Informational}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
