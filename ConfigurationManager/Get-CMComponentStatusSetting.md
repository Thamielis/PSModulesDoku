Get-CMComponentStatusSetting
----------------------------




### Synopsis
Get the settings for the site's component status summarizer.



---


### Description

Use this cmdlet to get the settings for the site's Component Status Summarizer . For more information, see Use the status system in Configuration Manager (/mem/configmgr/core/servers/manage/use-status-system#configure-status-reporting).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMComponentStatusMessage](Get-CMComponentStatusMessage)



* [Use the status system in Configuration Manager](Use the status system in Configuration Manager)





---


### Examples
#### Example 1: Get settings for components
```PowerShell
Get-CMComponentStatusSetting -ComponentName "SMS_REPL*"
```



---


### Parameters
#### **ComponentName**

Specify a name of a component. You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






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



#### **SiteSystemServerName**

Specify the name of a site system server that hosts a component.


> [!NOTE] > This parameter is deprecated and may be removed in a future release.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Name   |





---


### Inputs
None





---


### Outputs
* ComponentStatusSetting[]


* ComponentStatusSetting






---


### Notes




---


### Syntax
```PowerShell
Get-CMComponentStatusSetting [-ComponentName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteSystemServerName <String>] [<CommonParameters>]
```
