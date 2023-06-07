Get-CMAlertSubscription
-----------------------




### Synopsis
Get one or more alert subscription objects.



---


### Description

Use this cmdlet to get one or more Configuration Manager alert subscriptions and display their properties. Use subscriptions to send an email for an alert. For more information, see Configure email alerts (/mem/configmgr/core/servers/manage/configure-alerts#email-alerts).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAlertSubscription](New-CMAlertSubscription)



* [Set-CMAlertSubscription](Set-CMAlertSubscription)



* [Remove-CMAlertSubscription](Remove-CMAlertSubscription)



* [Configure email alerts](Configure email alerts)





---


### Examples
#### Example 1: Display all alert subscriptions
```PowerShell
Get-CMAlertSubscription
```

#### Example 2: Display alert subscriptions by ID by using wildcard characters
```PowerShell
Get-CMAlertSubscription -Id 16777*
```

#### Example 3: Display an alert subscription by name
```PowerShell
Get-CMAlertSubscription -Name "Subscription01"
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of a subscription. For example, `11`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Name**

Specify the name of an alert subscription.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_Subscription


* IResultObject#SMS_Subscription






---


### Notes
For more information on this return object and its properties, see SMS_Subscription server WMI class (/mem/configmgr/develop/reference/core/servers/manage/sms_subscription-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMAlertSubscription [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMAlertSubscription [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
