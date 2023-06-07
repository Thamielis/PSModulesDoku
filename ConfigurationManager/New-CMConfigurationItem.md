New-CMConfigurationItem
-----------------------




### Synopsis
Creates a Configuration Manager configuration item.



---


### Description

The New-CMConfigurationItem cmdlet creates a configuration item in Configuration Manager. Create configuration items to define configurations that you want to manage and assess for compliance on devices.



You can specify the ParentConfigurationItem parameter to create a child configuration item. Child configuration items in Configuration Manager are copies of configuration items that retain a relationship to the original configuration item; therefore, they inherit the original configuration from the parent configuration item. You cannot create child configuration items for mobile devices.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Introduction to Compliance Settings in Configuration Manager](Introduction to Compliance Settings in Configuration Manager)



* [Get-CMConfigurationItem](Get-CMConfigurationItem)



* [Get-CMConfigurationItemXMLDefinition](Get-CMConfigurationItemXMLDefinition)



* [Get-CMConfigurationItemHistory](Get-CMConfigurationItemHistory)



* [Set-CMConfigurationItem](Set-CMConfigurationItem)



* [Remove-CMConfigurationItem](Remove-CMConfigurationItem)



* [Import-CMConfigurationItem](Import-CMConfigurationItem)



* [Export-CMConfigurationItem](Export-CMConfigurationItem)



* [ConvertTo-CMConfigurationItem](ConvertTo-CMConfigurationItem)



* [ConvertFrom-CMConfigurationItem](ConvertFrom-CMConfigurationItem)





---


### Examples
#### Example 1: Create a configuration item
```PowerShell
PS XYZ:\> New-CMConfigurationItem -CreationType MobileDevice -Name "MD_Config88"
```
This command creates a configuration item for mobile devices named MD_Config88.


---


### Parameters
#### **Category**

Specifies an array of localized names of the categories to which the configuration item belongs.






|Type        |Required|Position|PipelineInput|Aliases                       |
|------------|--------|--------|-------------|------------------------------|
|`[String[]]`|false   |named   |False        |LocalizedCategoryInstanceNames|



#### **CreationType**

Specifies the type of configuration item. The acceptable values for this parameter are:


* MacOS


* MobileDevice


* None


* WindowsApplication


* WindowsOS



Valid Values:

* None
* WindowsApplication
* WindowsOS
* MacOS
* MobileDevice






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[CICreationType]`|true    |named   |False        |



#### **Description**

Specifies a description for a configuration item.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



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



#### **Name**

Specifies a name for the configuration item.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **ParentConfigurationItem**

Specifies a parent CMConfigurationItem object. To obtain a CMConfigurationItem object, use the Get-CMConfigurationItem (Get-CMConfigurationItem.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



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
* IResultObject#SMS_ConfigurationItem






---


### Notes




---


### Syntax
```PowerShell
New-CMConfigurationItem [-Category <String[]>] -CreationType {None | WindowsApplication | WindowsOS | MacOS | MobileDevice} [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMConfigurationItem [-Category <String[]>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -ParentConfigurationItem <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
