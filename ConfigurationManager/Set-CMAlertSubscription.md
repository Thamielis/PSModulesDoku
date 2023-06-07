Set-CMAlertSubscription
-----------------------




### Synopsis
Changes the properties of an alert subscription.



---


### Description

The Set-CMAlertSubscription cmdlet changes the properties of an alert subscription object in Configuration Manager. You can change the name of an alert subscription, the email address of the recipient of an alert notification, the Windows locale ID, and the alert ID. You can also change the security scope membership of an alert subscription by adding it to or removing it from a specified security scope.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAlertSubscription](New-CMAlertSubscription)



* [Get-CMAlertSubscription](Get-CMAlertSubscription)



* [Remove-CMAlertSubscription](Remove-CMAlertSubscription)



* [Set-CMSecurityScope](Set-CMSecurityScope)





---


### Examples
#### Example 1: Change the properties of an alert subscription by subscription ID
```PowerShell
PS XYZ:\> Set-CMAlertSubscription -Id "16777217" -NewName "Subscription02" -EmailAddress "evan.narvaez@contoso.com" -LocaleId 2057 -AlertIds 16777240
```
This command changes the name, email address, Windows locale ID, and alert ID of an alert subscription that has the ID 16777217.
#### Example 2: Change the properties of an alert subscription by subscription name
```PowerShell
PS XYZ:\> Set-CMAlertSubscription -Name "Subscription01" -NewName "Subscription02" -EmailAddress "elisa.daugherty@contoso.com" -LocaleId 2057 -AlertIds 16777240
```
This command changes the name, email address, Windows locale ID, and alert ID of an alert subscription named Subscription01.
#### Example 3: Change the properties of an alert subscription by using the output from another cmdlet as input
```PowerShell
PS XYZ:\> $SubObj = Get-CMAlertSubscription -Id "16777310"
PS XYZ:\> Set-CMAlertSubscription -AlertSubscription $SubObj -NewName "Subscription02" -EmailAddress "patti.fuller@contoso.com" -LocaleId 3081 -AlertIds 16777240
```
The first command gets an alert subscription object that has the ID 16777310, and then stores the object in the $SubObj variable.


The second command changes the properties of the alert subscription object, which include the subscription name, email recipient, locale ID, and alert ID, for the alert notification stored in the $SubObj variable.
#### Example 4: Add an alert subscription to a security scope
```PowerShell
PS XYZ:\> Set-CMAlertSubscription -SecurityScopeAction AddMembership -SecurityScopeName "Test" -Name "Subscription01"
```
This command adds the alert subscription named Subscription01 to the security scope named Test.
#### Example 5: Remove an alert subscription from a security scope
```PowerShell
PS XYZ:\> Set-CMAlertSubscription -SecurityScopeAction RemoveMembership -SecurityScopeName "Test" -Name "Subscription01"
```
This command removes the alert subscription named Subscription01 from the security scope named Test.


---


### Parameters
#### **AddEmailAddress**








|Type        |Required|Position|PipelineInput|Aliases          |
|------------|--------|--------|-------------|-----------------|
|`[String[]]`|false   |named   |False        |AddEmailAddresses|



#### **AlertId**

Specifies an array of alert IDs for subscriptions.






|Type       |Required|Position|PipelineInput|Aliases |
|-----------|--------|--------|-------------|--------|
|`[Int32[]]`|false   |named   |False        |AlertIds|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EmailAddress**

Specifies an email address where you want to send an alert notification. You can separate multiple email addresses by using a semicolon.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|false   |named   |False        |EmailAddresses|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the identifier for a subscription object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **InputObject**

Specifies an alert notification object in Configuration Manager.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



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



#### **NewName**

Specifies a new name for an alert subscription object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveEmailAddress**








|Type        |Required|Position|PipelineInput|Aliases             |
|------------|--------|--------|-------------|--------------------|
|`[String[]]`|false   |named   |False        |RemoveEmailAddresses|



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
Set-CMAlertSubscription [-AddEmailAddress <String[]>] [-AlertId <Int32[]>] [-DisableWildcardHandling] [-EmailAddress <String[]>] [-ForceWildcardHandling] -Id <String> [-LocaleId <Int32>] [-NewName <String>] [-PassThru] [-RemoveEmailAddress <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAlertSubscription [-AddEmailAddress <String[]>] [-AlertId <Int32[]>] [-DisableWildcardHandling] [-EmailAddress <String[]>] [-ForceWildcardHandling] -InputObject <IResultObject> [-LocaleId <Int32>] [-NewName <String>] [-PassThru] [-RemoveEmailAddress <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAlertSubscription [-AddEmailAddress <String[]>] [-AlertId <Int32[]>] [-DisableWildcardHandling] [-EmailAddress <String[]>] [-ForceWildcardHandling] [-LocaleId <Int32>] -Name <String> [-NewName <String>] [-PassThru] [-RemoveEmailAddress <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
