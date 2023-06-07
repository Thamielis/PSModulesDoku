Get-CMUser
----------




### Synopsis
Gets a Configuration Manager user.



---


### Description

The Get-CMUser cmdlet gets a Configuration Manager user object.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMUserCollectionDirectMembershipRule](Add-CMUserCollectionDirectMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Remove-CMUser](Remove-CMUser)





---


### Examples
#### Example 1: Get a user by name
```PowerShell
PS XYZ:\> Get-CMUser -CollectionName "All Users" -Name "Contoso\username01"
```
This command gets the user named username01 from the All Users collection.
#### Example 2: Pass a collection and get a user from it
```PowerShell
PS XYZ:\> Get-CMCollection -Name "All Users" | Get-CMUser -Name "Contoso\testuser01"
```
This command gets the collection object named All Users and uses the pipeline operator to pass the object to Get-CMUser , which gets the user named testuser01 from the collection object.


---


### Parameters
#### **CollectionId**

Specifies the ID of a user collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specifies the name of a user collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Specifies a collection object. To obtain a collection object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **Name**

Specifies the name of a user.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ResourceId**

Specifies the resource ID of a user.






|Type     |Required|Position|PipelineInput|Aliases      |
|---------|--------|--------|-------------|-------------|
|`[Int32]`|true    |named   |False        |Id<br/>UserId|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_CombinedUserResources


* IResultObject#SMS_CombinedUserResources






---


### Notes




---


### Syntax
```PowerShell
Get-CMUser -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
```PowerShell
Get-CMUser -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
```PowerShell
Get-CMUser [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Name <String>] [<CommonParameters>]
```
```PowerShell
Get-CMUser [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
```PowerShell
Get-CMUser [-DisableWildcardHandling] [-ForceWildcardHandling] -ResourceId <Int32> [<CommonParameters>]
```
