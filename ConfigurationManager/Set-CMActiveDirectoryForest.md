Set-CMActiveDirectoryForest
---------------------------




### Synopsis
Changes Active Directory forest properties in Configuration Manager.



---


### Description

The Set-CMActiveDirectoryForest cmdlet changes values for an Active Directory forest object in Configuration Manager. You can edit the description, enable or disable discovery, and specify a fully qualified domain name (FQDN) and publishing path. You can specify an Active Directory forest object by ID or FQDN, or you can supply the Active Directory forest object itself.



Active Directory Forest Discovery requires a global account to discover or publish to untrusted forests.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMActiveDirectoryForest](New-CMActiveDirectoryForest)



* [Get-CMActiveDirectoryForest](Get-CMActiveDirectoryForest)



* [Remove-CMActiveDirectoryForest](Remove-CMActiveDirectoryForest)



* [Get-CMActiveDirectorySite](Get-CMActiveDirectorySite)





---


### Examples
#### Example 1: Change the description of an Active Directory forest
```PowerShell
PS XYZ:\> Set-CMActiveDirectoryForest -Id "16777217" -Description "AD Forest 01"
```
This command changes the description of an Active Directory forest that has the ID 16777217 to AD Forest 01.


---


### Parameters
#### **AddPublishingSite**








|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|false   |named   |False        |AddPublishingSites|



#### **Description**

Specifies a description for an Active Directory forest object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableDiscovery**

Specifies whether to discover Active Directory sites and subnets. You must configure an Active Directory Forest Discovery method before you use this parameter. The default value is $False.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForestFqdn**

Specifies the FQDN of a Configuration Manager object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Id**

Specifies an array of IDs of Configuration Manager objects. You can find the identifier value in the ForestID property of an Active Directory forest.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[UInt32]`|true    |named   |False        |ForestId|



#### **InputObject**

Specifies an Active Directory forest object in Configuration Manager.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Password**

{{ Fill Password Description }}






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **PublishingPath**

Specifies one or more Configuration Manager sites that publish site information to an Active Directory forest. You can use a comma-separated list in quotation marks to specify more than one site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RemovePublishingSite**








|Type               |Required|Position|PipelineInput|Aliases              |
|-------------------|--------|--------|-------------|---------------------|
|`[IResultObject[]]`|false   |named   |False        |RemovePublishingSites|



#### **UserName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* IResultObject#SMS_ADForest






---


### Notes




---


### Syntax
```PowerShell
Set-CMActiveDirectoryForest [-AddPublishingSite <IResultObject[]>] [-Description <String>] [-DisableWildcardHandling] [-EnableDiscovery <Boolean>] [-ForceWildcardHandling] -ForestFqdn <String> [-PassThru] [-Password <SecureString>] [-PublishingPath <String>] [-RemovePublishingSite <IResultObject[]>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMActiveDirectoryForest [-AddPublishingSite <IResultObject[]>] [-Description <String>] [-DisableWildcardHandling] [-EnableDiscovery <Boolean>] [-ForceWildcardHandling] -Id <UInt32> [-PassThru] [-Password <SecureString>] [-PublishingPath <String>] [-RemovePublishingSite <IResultObject[]>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMActiveDirectoryForest [-AddPublishingSite <IResultObject[]>] [-Description <String>] [-DisableWildcardHandling] [-EnableDiscovery <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Password <SecureString>] [-PublishingPath <String>] [-RemovePublishingSite <IResultObject[]>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
