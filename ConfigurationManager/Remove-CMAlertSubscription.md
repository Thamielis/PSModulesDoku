Remove-CMAlertSubscription
--------------------------




### Synopsis
Removes an alert subscription object.



---


### Description

The Remove-CMAlertSubscription cmdlet removes an alert subscription from Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAlertSubscription](New-CMAlertSubscription)



* [Get-CMAlertSubscription](Get-CMAlertSubscription)



* [Set-CMAlertSubscription](Set-CMAlertSubscription)





---


### Examples
#### Example 1: Remove an alert subscription by ID
```PowerShell
PS XYZ:\> Remove-CMAlertSubscription -Id "16777310"
```
This command removes an alert subscription by using its ID.
#### Example 2: Remove an alert subscription by name
```PowerShell
PS XYZ:\> Remove-CMAlertSubscription -Name "Subscription01"
```
This command removes an alert subscription named Subscription01.
#### Example 3: Remove an alert subscription by using the output from another cmdlet
```PowerShell
PS XYZ:\> $SubObj = Get-CMAlertSubscription -Id "16777310"
PS XYZ:\> Remove-CMAlertSubscription -AlertSubscription $SubObj
```
The first command gets an alert subscription object that has the ID 16777310, and then stores the object in the $SubObj variable.


The second command deletes the alert subscription in $SubObj.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the ID of an alert subscription.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **InputObject**

Specifies an alert notification object in Configuration Manager.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies the name of an alert subscription.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMAlertSubscription [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAlertSubscription [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAlertSubscription [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
