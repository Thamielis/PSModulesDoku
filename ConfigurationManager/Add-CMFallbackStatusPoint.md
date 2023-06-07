Add-CMFallbackStatusPoint
-------------------------




### Synopsis
Add a fallback status point to a Configuration Manager site.



---


### Description

Use this cmdlet to add a fallback status point to a Configuration Manager site. The fallback status point is a site system role that helps you monitor client installation. It identifies clients that are unmanaged because they can't communicate with their management point. Although this role is supported only at primary sites, you can install multiple instances of this role at a site, and at multiple sites in the same hierarchy. For more information, see Determine the site system roles for Configuration Manager clients (/mem/configmgr/core/clients/deploy/plan/determine-the-site-system-roles-for-clients#fallback-status-point).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMFallbackStatusPoint](Get-CMFallbackStatusPoint)



* [Remove-CMFallbackStatusPoint](Remove-CMFallbackStatusPoint)



* [Set-CMFallbackStatusPoint](Set-CMFallbackStatusPoint)



* [Determine the site system roles for Configuration Manager clients](Determine the site system roles for Configuration Manager clients)





---


### Examples
#### Example 1: Add a fallback status point
```PowerShell
Add-CMFallbackStatusPoint -SiteCode "CM1" -SiteSystemServerName "CMFSPPoint.Western.Contoso.com" -StateMessageNum 10000 -ThrottleInterval 60
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



#### **InputObject**

Specify a site system server object as the target for this role. To get this object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteServer|



#### **SiteCode**

Specify the site code for this site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the FQDN of the server as the target for this role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **StateMessageCount**

Specify the number of state messages that Configuration Manager can process within the throttle interval. Use either ThrottleMins or ThrottleSec to configure the throttle interval.


When the site server processes many state messages, it might decrease the performance of the site server. For more information, see Configuration options for site system roles - Fallback status point (/mem/configmgr/core/servers/deploy/configure/configuration-options-for-site-system-roles#BKMK_Fallback_Status_Point).


By default, this value is `10000`.






|Type     |Required|Position|PipelineInput|Aliases                               |
|---------|--------|--------|-------------|--------------------------------------|
|`[Int32]`|false   |named   |False        |StateMessagesCount<br/>StateMessageNum|



#### **ThrottleMins**

Configure the throttle interval in minutes for how Configuration Manager processes the state messages. Use this parameter with StateMessageCount .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ThrottleSec**

Configure the throttle interval in seconds for how Configuration Manager processes the state messages. Use this parameter with StateMessageCount .


By default, this value is `3600`.






|Type     |Required|Position|PipelineInput|Aliases                                     |
|---------|--------|--------|-------------|--------------------------------------------|
|`[Int32]`|false   |named   |False        |ThrottleIntervalSeconds<br/>ThrottleInterval|



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
* IResultObject#SMS_SCI_SysResUse






---


### Notes
For more information on this return object and its properties, see SMS_SCI_SysResUse server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_sci_sysresuse-server-wmi-class).



---


### Syntax
```PowerShell
Add-CMFallbackStatusPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-StateMessageCount <Int32>] [-ThrottleMins <Int32>] [-ThrottleSec <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMFallbackStatusPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-StateMessageCount <Int32>] [-ThrottleMins <Int32>] [-ThrottleSec <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
