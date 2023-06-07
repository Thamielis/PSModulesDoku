ConvertFrom-CMIResultObject
---------------------------




### Synopsis
Converts from an IResultObject to a ManagementBaseObject .



---


### Description

The Convertfrom-CMIResultObject cmdlet converts from an IResultObject to a ManagementBaseObject .



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [ConvertTo-CMIResultObject](ConvertTo-CMIResultObject)





---


### Examples
#### Example 1: Convert an IResultObject to a ManagementBaseObject by getting a site object
```PowerShell
PS ABC:\> $Site = Get-CMSite -SiteCode PS1
PS ABC:\> ConvertFrom-CMIResultObject -InputObject $Site
```
The first command gets the site object with the code PS1 and stores the object in the $Site variable.


The second command converts the site stored in $Site to a ManagementBaseObject.
#### Example 2: Convert an IResultObject to a ManagementBaseObject by getting a site by its code
```PowerShell
PS ABC:\> ConvertFrom-CMIResultObject -InputObject (Get-CMSite -SiteCode PS2)
```
This command gets the site with the code PS2 and then converts the site to a ManagementBaseObject.


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

Specifies the IResultObject to convert to a ManagementBaseObject .






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|





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
ConvertFrom-CMIResultObject [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
