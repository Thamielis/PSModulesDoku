Enable-CMSiteFeature
--------------------




### Synopsis
Enable an optional feature.



---


### Description

Use this cmdlet to enable optional features for the site. For more information, see Enable optional features from updates (/mem/configmgr/core/servers/manage/install-in-console-updates#bkmk_options).



If a pre-release feature isn't enabled for the hierarchy, the cmdlet fails with an error message.



If the feature is already enabled for the site, the cmdlet returns a warning message.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSiteFeature](Get-CMSiteFeature)





---


### Examples
#### Example 1: Get a feature and enable it
```PowerShell
Get-CMSiteFeature -Fast -Name "Task Sequence Debugger" | Enable-CMSiteFeature
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a site feature object to enable. To get this object, use the Get-CMSiteFeature (Get-CMSiteFeature.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the site feature name to enable.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_CM_UpdateFeatures






---


### Notes
For more information on this return object and its properties, see SMS_CM_UpdateFeatures server WMI class (/mem/configmgr/develop/reference/sum/sms_cm_updatefeatures-server-wmi-class).



---


### Syntax
```PowerShell
Enable-CMSiteFeature [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Enable-CMSiteFeature [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
