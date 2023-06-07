Clear-CMSiteStatusMessageCount
------------------------------




### Synopsis
Clears the message count in Configuration Manager.



---


### Description

The Clear-CMSiteStatusMessageCount cmdlet clears the message count in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSiteStatusMessage](Get-CMSiteStatusMessage)





---


### Examples
#### Example 1: Clear the status message count
```PowerShell
PS XYZ:\>Clear-CMSiteStatusMessageCount -ComputerName "Contoso-Test" -Severity Error -SiteCode "CM1"
```
This command clears the error message count for the computer.


---


### Parameters
#### **ComputerName**

Specifies the name of a computer in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **Severity**

Specifies a message severity. The acceptable values for this parameter are: All, Error, Information, and Warning.



Valid Values:

* All
* Error
* Warning
* Information






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[Severity]`|true    |named   |False        |



#### **SiteCode**

Specifies a site code in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Clear-CMSiteStatusMessageCount -ComputerName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -Severity {All | Error | Warning | Information} [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
