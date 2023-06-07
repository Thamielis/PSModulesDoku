Get-CMSoftwareUpdateLicense
---------------------------




### Synopsis
Gets a EULA or SLT for a software update in Configuration Manager.



---


### Description

The Get-CMSoftwareUpdateLicense cmdlet gets an End User License Agreement (EULA) or Software License Terms (SLT) for a software update in Configuration Manager. You can specify a software update by ID or by name or use the Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)cmdlet to obtain one. If you specify an ID or name, you can further specify a security scope membership.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate)





---


### Examples
#### Example 1: Get a EULA or SLT for a software update
```PowerShell
PS XYZ:\> Get-CMSoftwareUpdateLicense -Name "UpdatePkg01" -SecuredScopeNames "SecScope02"
```
This command gets the EULA or SLT for a software update named UpdatePkg01 for the security scope named SecScope02.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EulaAcceptance**





Valid Values:

* Declined
* Accepted
* Unknown






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[EulaAcceptance]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a software update object. To obtain a software update object, use the Get-CMSoftwareUpdate cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies an array of names of software updates.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDisplayName|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [String[]](https://learn.microsoft.com/en-us/dotnet/api/System.String[])


* [String](https://learn.microsoft.com/en-us/dotnet/api/System.String)






---


### Notes




---


### Syntax
```PowerShell
Get-CMSoftwareUpdateLicense [-DisableWildcardHandling] [-EulaAcceptance {Declined | Accepted | Unknown}] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdateLicense [-DisableWildcardHandling] [-EulaAcceptance {Declined | Accepted | Unknown}] [-ForceWildcardHandling] [-Name <String>] [-PassThru] [<CommonParameters>]
```
