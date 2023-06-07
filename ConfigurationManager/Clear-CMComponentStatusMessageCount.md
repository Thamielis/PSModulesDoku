Clear-CMComponentStatusMessageCount
-----------------------------------




### Synopsis
Changes the component status message count to zero.



---


### Description

The Clear-CMComponentStatusMessageCount cmdlet changes the component status message count to zero (0).



Configuration Manager indicates whether operations succeed or fail and include other information in component status messages. Threads or processes send component status messages to Configuration Manager sites, identified by site codes.



You can define which message count to set to zero by the component that created the messages, severity of the messages, and the site code of the Configuration Manager server that receives the messages. You can also specify the computer that hosts that component.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMComponentStatusMessage](Get-CMComponentStatusMessage)





---


### Examples
#### Example 1: Clear message count
```PowerShell
PS XYZ:\>Clear-CMComponentStatusMessageCount -ComponentName "SMS_HIERARCHY_MANAGER" -Severity All -SiteCode "CM1"
```
This command changes the message count to zero for the component SMS_HIERARCHY_MANAGER for all message severity types. The command specifies the site that has the site code CM1.
#### Example 2: Clear error message count
```PowerShell
PS XYZ:\>Clear-CMComponentStatusMessageCount -ComponentName "SMS_DISTRIBUTION_MANAGER" -Severity Error -SiteCode "CM1" -ComputerName "West34.Western.Contoso.com"
```
This command changes the message count to zero for the component SMS_DISTRIBUTION_MANAGER for error messages. The command specifies the site that has the site code CM1, and includes the computer name West34.Western.Contoso.com.


---


### Parameters
#### **ComponentName**

Specifies the name of a component that creates messages.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ComputerName**

Specifies the name of a computer that hosts the component.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |MachineName|



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

Specifies the severity of a component status message. The acceptable values for this parameter are:


* All


* Error


* Information


* Warning



Valid Values:

* All
* Error
* Warning
* Information






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[Severity]`|true    |named   |False        |



#### **SiteCode**

Specifies the site code for a Configuration Manager site. Status messages originate in this site.






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
Clear-CMComponentStatusMessageCount -ComponentName <String> [-ComputerName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Severity {All | Error | Warning | Information} [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
