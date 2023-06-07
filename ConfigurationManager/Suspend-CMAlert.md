Suspend-CMAlert
---------------




### Synopsis
Suspends monitoring alerts.



---


### Description

The Suspend-CMAlert cmdlet suspends monitoring of an alert until a specified date. At that time, Configuration Manager updates the state of the alert. You can suspend an alert only when it is enabled. If you do not specify the SkipUntil parameter, the alert is suspended indefinitely.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMAlert](Enable-CMAlert)



* [Get-CMAlert](Get-CMAlert)



* [Remove-CMAlert](Remove-CMAlert)



* [Set-CMAlert](Set-CMAlert)



* [Disable-CMAlert](Disable-CMAlert)





---


### Examples
#### Example 1: Suspend an alert by using ID
```PowerShell
PS XYZ:\> Suspend-CMAlert -Id "16777219" -Comments "Postponing alert evaluation" -SkipUntil "Wednesday, August 20, 2012 4:03:17 PM"
```
This command suspends an alert that has the Id 16777219 until the time specified by SkipUntil , and adds a comment to the alert.
#### Example 2: Suspend an alert by using alert object variable
```PowerShell
PS XYZ:\> $AlertObj = Get-CMAlert -Id "16777221"
PS XYZ:\> Suspend-CMAlert -InputObject $AlertObj -Comments "Postponing alert evaluation" -SkipUntil "4/8/2012 8:04:39 PM"
```
The first command gets the alert object that has the ID 16777221, and then stores the object in the $AlertObj variable.


The second command suspends the alert stored in $AlertObj until the time specified by SkipUntil , and adds a comment to the alert.


---


### Parameters
#### **Comment**

Specifies a comment to add to the alert. You can use the comment to record the explanation for suspending the alert.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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

Specifies a CMAlert object. To obtain a CMAlert object, use the Get-CMAlert cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Alert  |



#### **Name**

Specifies the name of an alert. You can obtain the name of an alert by using Get-CMAlert .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SkipUntil**

Specifies a specific date and time to start evaluation of the alert. Enter a DateTime object or a string that can be converted to a time, such as April 19, 2012 15:00, 12/31/2013 9:00 PM, or 3am. To obtain a DateTime object, use the Get-Date cmdlet. For more information, type `Get-Help Get-Date`.


If you do not specify an element of the DateTime object, such as seconds, that element of the job trigger is not changed. If the original job trigger did not include a DateTime object and you omit an element, the job trigger is created with the corresponding element from the current date and time. DateTime objects, and strings that are converted to DateTime objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|true    |named   |False        |



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
Suspend-CMAlert [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-PassThru] -SkipUntil <DateTime> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Suspend-CMAlert [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] -SkipUntil <DateTime> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Suspend-CMAlert [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] -SkipUntil <DateTime> [-Confirm] [-WhatIf] [<CommonParameters>]
```
