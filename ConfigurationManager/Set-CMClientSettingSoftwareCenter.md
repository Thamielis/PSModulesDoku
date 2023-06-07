Set-CMClientSettingSoftwareCenter
---------------------------------




### Synopsis
Use this cmdlet to configure the client settings in the Software Center group.



---


### Description

Use this cmdlet to configure the client settings in the Software Center group.



> [!NOTE] > Configuration Manager cmdlets must be run from the Configuration Manager site drive. For more information, see the getting started (/powershell/sccm/overview)documentation.



---


### Related Links
* [About client settings - Software Center](About client settings - Software Center)



* [Plan for Software Center](Plan for Software Center)





---


### Examples
#### Example 1: Add custom tabs
```PowerShell
$itemA = New-CMSoftwareCenterTabItem -Name "1abc" -Url "http://www.a"
$itemB = New-CMSoftwareCenterTabItem -Name "2abc" -Url "https://www.b"
$itemC = New-CMSoftwareCenterTabItem -Name "3abc" -Url "http://www.c"
$itemD = New-CMSoftwareCenterTabItem -Name "4abc" -Url "https://www.d"
$itemE = New-CMSoftwareCenterTabItem -Name "5abc" -Url "http://www.e"
Set-CMClientSettingSoftwareCenter -DefaultSetting -AddCustomTab ($itemA, $itemB, $itemC, $itemD, $itemE)
```

#### Example 2: Hide a tab
```PowerShell
Set-CMClientSettingSoftwareCenter -DefaultSetting -SetInvisibleTabName ("2abc","4abc", "5abc")
```

#### Example 3: Remove a tab
```PowerShell
Set-CMClientSettingSoftwareCenter -DefaultSetting -RemoveCustomTabName ("3abc","4abc")
```

#### Example 4: Show a hidden tab
```PowerShell
Set-CMClientSettingSoftwareCenter -DefaultSetting -SetVisibleTabName ("2abc", "5abc")
```

#### Example 5: Change tab order
```PowerShell
# Move selected custom tab to specific position by name:
Set-CMClientSettingSoftwareCenter -DefaultSetting -SelectCustomTabName "1abc" -MoveSelectedTabToIndex 0

# Move selected built-in tab to specific position:
Set-CMClientSettingSoftwareCenter -DefaultSetting -SelectBuiltInTab AvailableSoftware -MoveSelectedTabToIndex 0

# Move selected tab to specific position by current index of position:
Set-CMClientSettingSoftwareCenter -DefaultSetting -SelectTabIndex 0 -MoveSelectedTabToIndex 1
```

#### Example 6: Change tab properties
```PowerShell
Set-CMClientSettingSoftwareCenter -DefaultSetting -SelectCustomTabName "1abc" -SelectedTabNewName "new1abc" -SelectedTabNewUrl http://www.aNew
```

#### Example 7: Remove custom tabs
```PowerShell
Set-CMClientSettingSoftwareCenter -DefaultSetting -ClearCustomTab
```



---


### Parameters
#### **AddCustomTab**

Use this parameter to add a custom tab to the Software Center client setting.






|Type                       |Required|Position|PipelineInput|Aliases      |
|---------------------------|--------|--------|-------------|-------------|
|`[SoftwareCenterTabItem[]]`|false   |named   |False        |AddCustomTabs|



#### **ClearCustomTab**

Use this parameter to remove a custom tab from the Software Center client setting.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Switch]`|false   |named   |False        |ClearAllCustomTabs|



#### **ColorScheme**

Use this parameter to configure the Software Center client setting, Color scheme for Software Center . Example color object for: Red=255, Green=74, Blue=74: $colorObject = [system.drawing.color]::FromArgb(255,255,74,74)






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Color]`|false   |named   |False        |



#### **CompanyName**

Use this parameter to configure the Software Center client setting, Company name .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CustomTabName**

This parameter is deprecated. To create a custom tab, use the New-CMSoftwareCenterTabItem (New-CMSoftwareCenterTabItem.md)cmdlet.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CustomTabUrl**

This parameter is deprecated. To create a custom tab, use the New-CMSoftwareCenterTabItem (New-CMSoftwareCenterTabItem.md)cmdlet.






|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[Uri]`|false   |named   |False        |



#### **DefaultSetting**

This parameter will apply settings to the default client setting. Use parameter -Name for any custom client setting.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableApplicationsTab**

Use this parameter to show or hide the default Applications tab in Software Center.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableComplianceTab**

Use this parameter to show or hide the default Device Compliance tab in Software Center.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableCustomize**

This parameter will enable custom Software Center settings. Like the color scheme or a logo.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableOperatingSystemsTab**

Use this parameter to show or hide the default Operating Systems tab in Software Center.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableOptionsTab**

Use this parameter to show or hide the default Options tab in Software Center.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableStatusTab**

Use this parameter to show or hide the default Installation Status tab in Software Center.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUpdatesTab**

Use this parameter to show or hide the default Updates tab in Software Center.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **HideApplicationCatalogLink**

Use this parameter to enable or disable the following client setting in the Software Center group: Hide Application Catalog link in Software Center






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **HideInstalledApplication**

Use this parameter to enable or disable the following client setting in the Software Center group: Hide installed applications in Software Center






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **HideUnapprovedApplication**

Use this parameter to enable or disable the following client setting in the Software Center group: Hide unapproved applications in Software Center






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**

Object of Get-CMClientSetting






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **LogoFilePath**

Use this parameter to specify the file path to an image to display as the logo in Software Center.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MoveSelectedTabToIndex**

Use this parameter to change the order of tabs in Software Center. Specify an integer for position, with `0` at the top. Use one of the following parameters to select the tab to move: SelectCustomTabName , SelectBuiltInTab , SelectTabIndex .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Name**

Use this parameter to specify a client setting by its name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveCustomTabName**

Specify the name of a custom tab to remove from the client setting. You can set one or more names.






|Type        |Required|Position|PipelineInput|Aliases             |
|------------|--------|--------|-------------|--------------------|
|`[String[]]`|false   |named   |False        |RemoveCustomTabNames|



#### **SelectBuiltInTab**

Use this parameter to select one of the built-in tabs in Software Center. Use one of the following parameters in the same command to change the tab's configuration: MoveSelectedTabToIndex , SelectedTabNewName , SelectedTabNewUrl .



Valid Values:

* AvailableSoftware
* Updates
* Osd
* InstallationStatus
* Compliance
* Options






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[BuiltInTab]`|false   |named   |False        |



#### **SelectCustomTabName**

Use this parameter to select by name a custom tab in Software Center. Use one of the following parameters in the same command to change the tab's configuration: MoveSelectedTabToIndex , SelectedTabNewName , SelectedTabNewUrl .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SelectedTabNewName**

In the same command when you select a tab, use this parameter to change the name of the tab.






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|false   |named   |False        |SelectedCustomTabNewName|



#### **SelectedTabNewUrl**

In the same command when you select a tab, use this parameter to change the URL of the tab.






|Type   |Required|Position|PipelineInput|Aliases                |
|-------|--------|--------|-------------|-----------------------|
|`[Uri]`|false   |named   |False        |SelectedCustomTabNewUrl|



#### **SelectTabIndex**

Use this parameter to select a tab by order in Software Center. Specify an integer for position, with `0` at the top. Use one of the following parameters in the same command to change the tab's configuration: MoveSelectedTabToIndex , SelectedTabNewName , SelectedTabNewUrl .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SetInvisibleTabName**

Use this parameter to hide a custom tab based upon its name. You can specify one or more tabs.






|Type        |Required|Position|PipelineInput|Aliases                   |
|------------|--------|--------|-------------|--------------------------|
|`[String[]]`|false   |named   |False        |SetInvisibleCustomTabNames|



#### **SetVisibleTabName**

Use this parameter to show a custom tab based upon its name. You can specify one or more tabs.






|Type        |Required|Position|PipelineInput|Aliases                 |
|------------|--------|--------|-------------|------------------------|
|`[String[]]`|false   |named   |False        |SetVisibleCustomTabNames|



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
Set-CMClientSettingSoftwareCenter [-AddCustomTab <SoftwareCenterTabItem[]>] [-ClearCustomTab] [-ColorScheme <Color>] [-CompanyName <String>] [-CustomTabName <String>] [-CustomTabUrl <Uri>] -DefaultSetting [-DisableWildcardHandling] [-EnableApplicationsTab <Boolean>] [-EnableComplianceTab <Boolean>] [-EnableCustomize <Boolean>] [-EnableOperatingSystemsTab <Boolean>] [-EnableOptionsTab <Boolean>] [-EnableStatusTab <Boolean>] [-EnableUpdatesTab <Boolean>] [-ForceWildcardHandling] [-HideApplicationCatalogLink <Boolean>] [-HideInstalledApplication <Boolean>] [-HideUnapprovedApplication <Boolean>] [-LogoFilePath <String>] [-MoveSelectedTabToIndex <Int32>] [-PassThru] [-RemoveCustomTabName <String[]>] [-SelectBuiltInTab {AvailableSoftware | Updates | Osd | InstallationStatus | Compliance | Options}] [-SelectCustomTabName <String>] [-SelectedTabNewName <String>] [-SelectedTabNewUrl <Uri>] [-SelectTabIndex <Int32>] [-SetInvisibleTabName <String[]>] [-SetVisibleTabName <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingSoftwareCenter [-AddCustomTab <SoftwareCenterTabItem[]>] [-ClearCustomTab] [-ColorScheme <Color>] [-CompanyName <String>] [-CustomTabName <String>] [-CustomTabUrl <Uri>] [-DisableWildcardHandling] [-EnableApplicationsTab <Boolean>] [-EnableComplianceTab <Boolean>] [-EnableCustomize <Boolean>] [-EnableOperatingSystemsTab <Boolean>] [-EnableOptionsTab <Boolean>] [-EnableStatusTab <Boolean>] [-EnableUpdatesTab <Boolean>] [-ForceWildcardHandling] [-HideApplicationCatalogLink <Boolean>] [-HideInstalledApplication <Boolean>] [-HideUnapprovedApplication <Boolean>] -InputObject <IResultObject> [-LogoFilePath <String>] [-MoveSelectedTabToIndex <Int32>] [-PassThru] [-RemoveCustomTabName <String[]>] [-SelectBuiltInTab {AvailableSoftware | Updates | Osd | InstallationStatus | Compliance | Options}] [-SelectCustomTabName <String>] [-SelectedTabNewName <String>] [-SelectedTabNewUrl <Uri>] [-SelectTabIndex <Int32>] [-SetInvisibleTabName <String[]>] [-SetVisibleTabName <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingSoftwareCenter [-AddCustomTab <SoftwareCenterTabItem[]>] [-ClearCustomTab] [-ColorScheme <Color>] [-CompanyName <String>] [-CustomTabName <String>] [-CustomTabUrl <Uri>] [-DisableWildcardHandling] [-EnableApplicationsTab <Boolean>] [-EnableComplianceTab <Boolean>] [-EnableCustomize <Boolean>] [-EnableOperatingSystemsTab <Boolean>] [-EnableOptionsTab <Boolean>] [-EnableStatusTab <Boolean>] [-EnableUpdatesTab <Boolean>] [-ForceWildcardHandling] [-HideApplicationCatalogLink <Boolean>] [-HideInstalledApplication <Boolean>] [-HideUnapprovedApplication <Boolean>] [-LogoFilePath <String>] [-MoveSelectedTabToIndex <Int32>] -Name <String> [-PassThru] [-RemoveCustomTabName <String[]>] [-SelectBuiltInTab {AvailableSoftware | Updates | Osd | InstallationStatus | Compliance | Options}] [-SelectCustomTabName <String>] [-SelectedTabNewName <String>] [-SelectedTabNewUrl <Uri>] [-SelectTabIndex <Int32>] [-SetInvisibleTabName <String[]>] [-SetVisibleTabName <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
