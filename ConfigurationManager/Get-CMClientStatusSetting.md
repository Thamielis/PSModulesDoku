Get-CMClientStatusSetting
-------------------------




### Synopsis
Gets client status settings.



---


### Description

The Get-CMClientStatusSetting cmdlet gets client status settings for the local computer. These settings determine the data collection intervals for individual client monitoring activities.



For more information about client settings, see About Client Settings in Configuration Manager (/mem/configmgr/core/clients/deploy/about-client-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [About Client Settings in Configuration Manager](About Client Settings in Configuration Manager)



* [Set-CMClientStatusSetting](Set-CMClientStatusSetting)



* [Update-CMClientStatus](Update-CMClientStatus)





---


### Examples
#### Example 1: Get client status settings for the local computer
```PowerShell
PS XYZ:\> Get-CMClientStatusSetting
ADRetrieving Schedule  :
CleanUpInterval        : 7
DDRInactiveInterval    : 3
HWInactiveInterval     : 4
NeedADLastLogonTime    :
PolicyInactiveInterval : 3
SettingsID             : 1
StatusInactiveInterval : 6
SWInactiveInterval     : 5
```
This command gets client status settings for the local computer.


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





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_CH_Settings


* IResultObject#SMS_CH_Settings






---


### Notes




---


### Syntax
```PowerShell
Get-CMClientStatusSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
