Set-CMFallbackStatusPoint
-------------------------




### Synopsis
Changes the throttle interval or the message count for a Configuration Manager fallback status point.



---


### Description

The Set-CMFallbackStatusPoint cmdlet changes the throttle interval or the message count for a fallback status point. A fallback status point is a site system role. You can specify the site system name and site code for a fallback status point or use the Get-CMFallbackStatusPoint (Get-CMFallbackStatusPoint.md)cmdlet to obtain a fallback status point object.



Configuration Manager can use one or more fallback status points to collect state messages for a site and send them to a server that is running Configuration Manager. Throttling prevents the fallback status point from sending too many messages together, which can affect performance. You can use the StateMessagesCount and ThrottleMinutesInterval parameters to limit how many messages a fallback status point sends during a defined period.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMFallbackStatusPoint](Add-CMFallbackStatusPoint)



* [Get-CMFallbackStatusPoint](Get-CMFallbackStatusPoint)



* [Remove-CMFallbackStatusPoint](Remove-CMFallbackStatusPoint)





---


### Examples
#### Example 1: Change message and threshold settings for a fallback status point
```PowerShell
PS XYZ:\> $CMFSP = Get-CMFallbackStatusPoint -SiteCode "CM1" -SiteSystemServerName "Server21.West01.Contoso.com"
PS XYZ:\> Set-CMFallbackStatusPoint -InputObject $CMFSP -StateMessagesCount 1000 -ThrottleMinutesInterval 60
```
The first command gets a fallback status point for the site that has the site code CM1 and the system name Server21.West01.Contoso.com and stores that object in the $CMFSP variable.


The second command sets the count of state messages to 1,000 and the throttle interval to 60 minutes for the object stored in $CMFSP.
#### Example 2: Change message and threshold settings
```PowerShell
PS XYZ:\> Set-CMFallbackStatusPoint -SiteCode "CM1" -SiteSystemServerName "Server21.West01.Contoso.com" -StateMessagesCount 1000 -ThrottleMinutesInterval 60
```
This command sets the count of state messages to 1,000 and the throttle interval to 60 minutes for the fallback status point for the site that has the site code CM1 and the system name Server21.West01.Contoso.com.


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

Specifies a fallback status point role. To obtain a fallback status point role, use the Get-CMFallbackStatusPoint (Get-CMFallbackStatusPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|FallbackStatusPoint|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code for a fallback status point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the site system name for a fallback status point.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **StateMessageCount**








|Type     |Required|Position|PipelineInput|Aliases                               |
|---------|--------|--------|-------------|--------------------------------------|
|`[Int32]`|false   |named   |False        |StateMessagesCount<br/>StateMessageNum|



#### **ThrottleMins**








|Type     |Required|Position|PipelineInput|Aliases                |
|---------|--------|--------|-------------|-----------------------|
|`[Int32]`|false   |named   |False        |ThrottleMinutesInterval|



#### **ThrottleSec**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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




---


### Syntax
```PowerShell
Set-CMFallbackStatusPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-StateMessageCount <Int32>] [-ThrottleMins <Int32>] [-ThrottleSec <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMFallbackStatusPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-SiteCode <String>] [-StateMessageCount <Int32>] [-ThrottleMins <Int32>] [-ThrottleSec <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
