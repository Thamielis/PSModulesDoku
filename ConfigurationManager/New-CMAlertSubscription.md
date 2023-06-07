New-CMAlertSubscription
-----------------------




### Synopsis
Creates an alert subscription object.



---


### Description

The New-CMAlertSubscription cmdlet creates a subscription that sends alert notifications to one or more users when specific events occur in Configuration Manager. Before you create an alert subscription, make sure that you have configured email settings for sending alert notifications, and that you have at least one alert configured in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAlertSubscription](Get-CMAlertSubscription)



* [Set-CMAlertSubscription](Set-CMAlertSubscription)



* [Remove-CMAlertSubscription](Remove-CMAlertSubscription)





---


### Examples
#### Example 1: Create an alert subscription
```PowerShell
PS XYZ:\> New-CMAlertSubscription -Name "Subscription01" -EmailAddress "evan.narvaez@contoso.com" -LocaleId 1033 -AlertIds 16777219
```
This command creates an alert subscription named Subscription01. If there is an event that pertains to the specified alert, this subscription sends alert notifications to an email recipient. Because the command specifies a locale ID of 1033, the subscription uses US English.


---


### Parameters
#### **AddEmailAddress**








|Type        |Required|Position|PipelineInput|Aliases                                              |
|------------|--------|--------|-------------|-----------------------------------------------------|
|`[String[]]`|true    |named   |False        |EmailAddresses<br/>EmailAddress<br/>AddEmailAddresses|



#### **AlertId**

Specifies an array of alert identifiers for the subscription.






|Type       |Required|Position|PipelineInput|Aliases |
|-----------|--------|--------|-------------|--------|
|`[Int32[]]`|false   |named   |False        |AlertIds|



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



#### **LocaleId**

Specifies a locale for alert messages. For more information and a list of locale identifiers, see Appendix A: Product Behavior (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Name**

Specifies the name of an alert subscription object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RequireValidLocaleId**








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
* IResultObject#SMS_Subscription






---


### Notes




---


### Syntax
```PowerShell
New-CMAlertSubscription -AddEmailAddress <String[]> [-AlertId <Int32[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-LocaleId <Int32>] -Name <String> [-RequireValidLocaleId] [-Confirm] [-WhatIf] [<CommonParameters>]
```
