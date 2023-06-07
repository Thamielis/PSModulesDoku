Set-CMBaseline
--------------




### Synopsis
Change the settings of configuration baselines.



---


### Description

Use this cmdlet to change the settings of a configuration baseline in Configuration Manager. A configuration baseline can include the following types of configuration data:



- Configuration items



- Other configuration baselines



- Software updates






The Configuration Manager client evaluates its compliance against this baseline. If all of the specified items are compliant, then the baseline itself is assessed as compliant. You can also include optional items, which are only evaluated if the relevant application or setting exists on the device.



For more information, see Create configuration baselines in Configuration Manager (/mem/configmgr/compliance/deploy-use/create-configuration-baselines).


> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).




---


### Related Links
* [Disable-CMBaseline](Disable-CMBaseline)



* [Enable-CMBaseline](Enable-CMBaseline)



* [Export-CMBaseline](Export-CMBaseline)



* [Get-CMBaseline](Get-CMBaseline)



* [Import-CMBaseline](Import-CMBaseline)



* [New-CMBaseline](New-CMBaseline)



* [Remove-CMBaseline](Remove-CMBaseline)



* [Get-CMBaselineXMLDefinition](Get-CMBaselineXMLDefinition)



* [Get-CMBaselineSummarizationSchedule](Get-CMBaselineSummarizationSchedule)



* [Create configuration baselines in Configuration Manager](Create configuration baselines in Configuration Manager)





---


### Examples
#### Example 1: Configure a configuration baseline
```PowerShell
$objPSTestWinAppCI = Get-CMConfigurationItem -Name PSTestWinAppCI
$objPSTestWinAppCI2 = Get-CMConfigurationItem -Name PSTestWinAppCI2
$objPSTestWinOSCI = Get-CMConfigurationItem -Name PSTestWinOSCI
$objPSTestWinAppCI3 = Get-CMConfigurationItem -Name PSTestWinAppCI3
$objPSTestWinAppCI4 = Get-CMConfigurationItem -Name PSTestWinAppCI4
$objPSTestMDCI = Get-CMConfigurationItem -Name PSTestMDCI
$objPSTestMacCI = Get-CMConfigurationItem -Name PSTestMacCI

$parameters = @{
  Name = "PSTestBaseLine"
  NewName = "PSTestBaseLineNew"
  Description = "DCM Testing New"
  RemoveCategory = ("IT Infrastructure")
  AddRequiredConfigurationItems = ($objPSTestWinAppCI4.CI_ID,$objPSTestMDCI.CI_ID)
  AddProhibitedConfigurationItems = ($objPSTestWinAppCI.CI_ID)
  AddOSConfigurationItems = ($objPSTestWinOSCI.CI_ID,$objPSTestMacCI.CI_ID)
  AddOptionalConfigurationItems = ($objPSTestWinAppCI2.CI_ID,$objPSTestWinAppCI3.CI_ID)
}

Set-CMBaseline @parameters
```

#### Example 2: Add a custom category
```PowerShell
$category = New-CMCategory -CategoryType BaselineCategories -Name "Accounting"
Set-CMBaseline -Name "Accounting baseline" -AddCategory $category.LocalizedCategoryInstanceName
```



---


### Parameters
#### **AddBaseline**

Specify an array of baseline IDs to add as configuration data to the target baseline. This value is the CI_ID property of the baseline, for example, `16777516`.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|false   |named   |False        |AddBaselines|



#### **AddCategory**

Specify an array of configuration category names to add to the configuration baselines. These categories improve searching and filtering. By default, the site includes the following categories for configuration baselines:


* Client


* IT Infrastructure


* Line of Business


* Server




To use another category, first add it with the New-CMCategory (New-CMCategory.md)cmdlet and `-CategoryType BaselineCategories` parameter.







|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **AddOptionalConfigurationItem**

Specify an array of configuration item IDs to add with an optional purpose. The Configuration Manager client only evaluates optional items if the relevant application exists on the device.


This value is the CI_ID property of the configuration item, for example, `16777514`.






|Type        |Required|Position|PipelineInput|Aliases                      |
|------------|--------|--------|-------------|-----------------------------|
|`[String[]]`|false   |named   |False        |AddOptionalConfigurationItems|



#### **AddOSConfigurationItem**

Specify an array of configuration item IDs to add of type OS . This value is the CI_ID property of the configuration item, for example, `16777514`.






|Type        |Required|Position|PipelineInput|Aliases                |
|------------|--------|--------|-------------|-----------------------|
|`[String[]]`|false   |named   |False        |AddOSConfigurationItems|



#### **AddProhibitedConfigurationItem**

Specify an array of configuration item IDs to add with a prohibited purpose. This value is the CI_ID property of the configuration item, for example, `16777514`.






|Type        |Required|Position|PipelineInput|Aliases                        |
|------------|--------|--------|-------------|-------------------------------|
|`[String[]]`|false   |named   |False        |AddProhibitedConfigurationItems|



#### **AddRequiredConfigurationItem**

Specify an array of configuration item IDs to add with a required purpose. This value is the CI_ID property of the configuration item, for example, `16777514`.






|Type        |Required|Position|PipelineInput|Aliases                      |
|------------|--------|--------|-------------|-----------------------------|
|`[String[]]`|false   |named   |False        |AddRequiredConfigurationItems|



#### **AddSoftwareUpdate**

Specify an array of software update IDs to add.






|Type        |Required|Position|PipelineInput|Aliases           |
|------------|--------|--------|-------------|------------------|
|`[String[]]`|false   |named   |False        |AddSoftwareUpdates|



#### **AllowComanagedClients**

Set this parameter to `$true` to always apply this baseline even for co-managed clients.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClearBaseline**

Add this parameter to remove all baselines as evaluation conditions from the target baseline. To remove individual baselines, use the RemoveBaseline parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClearOptionalConfigurationItem**

Add this parameter to remove all optional configuration items as evaluation conditions from the target baseline. To remove individual optional CIs, use the RemoveOptionalConfigurationItem parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClearOSConfigurationItem**

Add this parameter to remove all OS configuration items as evaluation conditions from the target baseline. To remove individual OS CIs, use the RemoveOSConfigurationItem parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClearProhibitedConfigurationItem**

Add this parameter to remove all prohibited configuration items as evaluation conditions from the target baseline. To remove individual prohibited CIs, use the RemoveProhibitedConfigurationItem parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClearRequiredConfigurationItem**

Add this parameter to remove all required configuration items as evaluation conditions from the target baseline. To remove individual required CIs, use the RemoveRequiredConfigurationItem parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClearSoftwareUpdate**

Add this parameter to remove all software updates as evaluation conditions from the target baseline. To remove individual software updates, use the RemoveSoftwareUpdate parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Description**

Specify an optional description of the configuration baseline to help identify it.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



#### **DesiredConfigurationDigestPath**

Specify a path to the configuration data stored as an XML digest.






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



#### **Id**

Specify the CI_ID of the configuration baseline to configure. For example, `16777516`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify a configuration baseline object to configure. To get this object, use the Get-CMBaseline (Get-CMBaseline.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of the configuration baseline to configure.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **NewName**

Specify a new name for the configuration baseline. Use this parameter to rename the target baseline.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveBaseline**

Specify an array of baseline IDs to remove as configuration data from the target baseline. This value is the CI_ID property of the baseline, for example, `16777516`. To remove all baselines as configuration data from this baseline, use the ClearBaseline parameter.






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|false   |named   |False        |RemoveBaselines|



#### **RemoveCategory**

Specify an array of configuration category names to remove from the configuration baseline.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **RemoveOptionalConfigurationItem**

Specify an array of optional CI IDs to remove as configuration data from the target baseline. This value is the CI_ID property of the configuration item, for example, `16777514`. To remove all optional configuration items from this baseline, use the ClearOptionalConfigurationItem parameter.






|Type        |Required|Position|PipelineInput|Aliases                         |
|------------|--------|--------|-------------|--------------------------------|
|`[String[]]`|false   |named   |False        |RemoveOptionalConfigurationItems|



#### **RemoveOSConfigurationItem**

Specify an array of OS CI IDs to remove as configuration data from the target baseline. This value is the CI_ID property of the configuration item, for example, `16777514`. To remove all OS configuration items from this baseline, use the ClearOSConfigurationItem parameter.






|Type        |Required|Position|PipelineInput|Aliases                   |
|------------|--------|--------|-------------|--------------------------|
|`[String[]]`|false   |named   |False        |RemoveOSConfigurationItems|



#### **RemoveProhibitedConfigurationItem**

Specify an array of prohibited CI IDs to remove as configuration data from the target baseline. This value is the CI_ID property of the configuration item, for example, `16777514`. To remove all prohibited configuration items from this baseline, use the ClearProhibitedConfigurationItem parameter.






|Type        |Required|Position|PipelineInput|Aliases                           |
|------------|--------|--------|-------------|----------------------------------|
|`[String[]]`|false   |named   |False        |RemoveProhibitedConfigurationItems|



#### **RemoveRequiredConfigurationItem**

Specify an array of required CI IDs to remove as configuration data from the target baseline. This value is the CI_ID property of the configuration item, for example, `16777514`. To remove all required configuration items from this baseline, use the ClearRequiredConfigurationItem parameter.






|Type        |Required|Position|PipelineInput|Aliases                         |
|------------|--------|--------|-------------|--------------------------------|
|`[String[]]`|false   |named   |False        |RemoveRequiredConfigurationItems|



#### **RemoveSoftwareUpdate**

Specify an array of software update IDs to remove as configuration data from the target baseline. To remove all software updates from this baseline, use the ClearSoftwareUpdate parameter.






|Type        |Required|Position|PipelineInput|Aliases              |
|------------|--------|--------|-------------|---------------------|
|`[String[]]`|false   |named   |False        |RemoveSoftwareUpdates|



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
Set-CMBaseline [-AddBaseline <String[]>] [-AddCategory <String[]>] [-AddOptionalConfigurationItem <String[]>] [-AddOSConfigurationItem <String[]>] [-AddProhibitedConfigurationItem <String[]>] [-AddRequiredConfigurationItem <String[]>] [-AddSoftwareUpdate <String[]>] [-AllowComanagedClients <Boolean>] [-ClearBaseline] [-ClearOptionalConfigurationItem] [-ClearOSConfigurationItem] [-ClearProhibitedConfigurationItem] [-ClearRequiredConfigurationItem] [-ClearSoftwareUpdate] [-Description <String>] [-DesiredConfigurationDigestPath <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-NewName <String>] [-PassThru] [-RemoveBaseline <String[]>] [-RemoveCategory <String[]>] [-RemoveOptionalConfigurationItem <String[]>] [-RemoveOSConfigurationItem <String[]>] [-RemoveProhibitedConfigurationItem <String[]>] [-RemoveRequiredConfigurationItem <String[]>] [-RemoveSoftwareUpdate <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBaseline [-AddBaseline <String[]>] [-AddCategory <String[]>] [-AddOptionalConfigurationItem <String[]>] [-AddOSConfigurationItem <String[]>] [-AddProhibitedConfigurationItem <String[]>] [-AddRequiredConfigurationItem <String[]>] [-AddSoftwareUpdate <String[]>] [-AllowComanagedClients <Boolean>] [-ClearBaseline] [-ClearOptionalConfigurationItem] [-ClearOSConfigurationItem] [-ClearProhibitedConfigurationItem] [-ClearRequiredConfigurationItem] [-ClearSoftwareUpdate] [-Description <String>] [-DesiredConfigurationDigestPath <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-RemoveBaseline <String[]>] [-RemoveCategory <String[]>] [-RemoveOptionalConfigurationItem <String[]>] [-RemoveOSConfigurationItem <String[]>] [-RemoveProhibitedConfigurationItem <String[]>] [-RemoveRequiredConfigurationItem <String[]>] [-RemoveSoftwareUpdate <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBaseline [-AddBaseline <String[]>] [-AddCategory <String[]>] [-AddOptionalConfigurationItem <String[]>] [-AddOSConfigurationItem <String[]>] [-AddProhibitedConfigurationItem <String[]>] [-AddRequiredConfigurationItem <String[]>] [-AddSoftwareUpdate <String[]>] [-AllowComanagedClients <Boolean>] [-ClearBaseline] [-ClearOptionalConfigurationItem] [-ClearOSConfigurationItem] [-ClearProhibitedConfigurationItem] [-ClearRequiredConfigurationItem] [-ClearSoftwareUpdate] [-Description <String>] [-DesiredConfigurationDigestPath <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-RemoveBaseline <String[]>] [-RemoveCategory <String[]>] [-RemoveOptionalConfigurationItem <String[]>] [-RemoveOSConfigurationItem <String[]>] [-RemoveProhibitedConfigurationItem <String[]>] [-RemoveRequiredConfigurationItem <String[]>] [-RemoveSoftwareUpdate <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
