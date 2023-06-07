Get-CMAlert
-----------




### Synopsis
Get Configuration Manager alerts.



---


### Description

Use this cmdlet to get one or more Configuration Manager alerts. You can get a specific alert by specifying the name or ID of the alert.



Configuration Manager generates alerts from certain operations when a specific condition occurs. Typically, it generates alerts when an error occurs that you need to resolve. For more information, see Configure alerts in Configuration Manager (/mem/configmgr/core/servers/manage/configure-alerts).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMAlert](Enable-CMAlert)



* [Remove-CMAlert](Remove-CMAlert)



* [Set-CMAlert](Set-CMAlert)



* [Suspend-CMAlert](Suspend-CMAlert)



* [Disable-CMAlert](Disable-CMAlert)



* [Configure alerts in Configuration Manager](Configure alerts in Configuration Manager)





---


### Examples
#### Example 1: Get all alerts
```PowerShell
Get-CMAlert
```

#### Example 2: Get alerts by using name
```PowerShell
Get-CMAlert -Name "$*" | Select-Object Id, Name, AlertState
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

Specify an alert ID. For example, `33554436`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Name**

Specify an alert name. You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character




Alerts whose name begins with the `$` character are default, system alerts.







|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |0       |False        |



#### **TypeId**

Specify the identifier for this type of alert.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TypeInstanceId**

Specify the user-defined identifier.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject#SMS_Alert


* IResultObject#SMS_CHAlert


* IResultObject#SMS_EPAlert






---


### Notes
For more information on these return objects and their properties, see the following articles:

- SMS_Alert server WMI class (/mem/configmgr/develop/reference/core/servers/manage/sms_alert-server-wmi-class)- SMS_CHAlert server WMI class (/mem/configmgr/develop/reference/core/servers/manage/sms_chalert-server-wmi-class)- SMS_EPAlert server WMI class (/mem/configmgr/develop/reference/core/servers/manage/sms_epalert-server-wmi-class)



---


### Syntax
```PowerShell
Get-CMAlert [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMAlert [[-Name] <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-TypeId <Int32>] [-TypeInstanceId <String>] [<CommonParameters>]
```
