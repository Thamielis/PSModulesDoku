Get-CMSiteFeature
-----------------




### Synopsis
Get an optional feature.



---


### Description

Use this cmdlet to get optional features for the site. For more information, see Enable optional features from updates (/mem/configmgr/core/servers/manage/install-in-console-updates#bkmk_options).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMSiteFeature](Enable-CMSiteFeature)





---


### Examples
#### Example 1: Get all pre-release features
```PowerShell
Get-CMSiteFeature -Prerelease -Fast
```

#### Example 2: Get a specific feature
```PowerShell
Get-CMSiteFeature -Name "Task Sequence Debugger"
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



#### **Name**

Specify the name of the optional feature to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Prerelease**

Add this parameter to filter the results on pre-release features. For more information, see Pre-release features in Configuration Manager (/mem/configmgr/core/servers/manage/pre-release-features).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Production**

Add this parameter to filter the results to features that aren't optional.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject#SMS_CM_UpdateFeatures






---


### Notes
For more information on this return object and its properties, see SMS_CM_UpdateFeatures server WMI class (/mem/configmgr/develop/reference/sum/sms_cm_updatefeatures-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMSiteFeature [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [-Prerelease] [-Production] [<CommonParameters>]
```
