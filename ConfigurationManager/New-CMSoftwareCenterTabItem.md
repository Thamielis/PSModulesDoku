New-CMSoftwareCenterTabItem
---------------------------




### Synopsis
Create a custom Software Center tab.



---


### Description

Use this cmdlet to create a custom Software Center tab.



For more information, see Plan for Software Center (/mem/configmgr/apps/plan-design/plan-for-software-center).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMClientSettingSoftwareCenter](Set-CMClientSettingSoftwareCenter)



* [Plan for Software Center](Plan for Software Center)





---


### Examples
#### Example 1: Create a helpdesk tab
```PowerShell
New-CMSoftwareCenterTabItem -Name "Helpdesk" -Url https://helpdesk.contoso.com
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



#### **Name**

Specify the name of the custom tab, which displays in the Software Center menu.






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[String]`|true    |named   |False        |CustomTabName|



#### **Url**

Specify the URL for Software Center to display when a user selects this tab.






|Type   |Required|Position|PipelineInput|Aliases     |
|-------|--------|--------|-------------|------------|
|`[Uri]`|true    |named   |False        |CustomTabUrl|





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMSoftwareCenterTabItem [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -Url <Uri> [<CommonParameters>]
```
