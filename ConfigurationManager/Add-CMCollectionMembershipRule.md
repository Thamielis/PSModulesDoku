Add-CMCollectionMembershipRule
------------------------------




### Synopsis
For system use only to add membership rules to collections.



---


### Description

This cmdlet is used by other cmdlets to create membership rules. Don't directly use this cmdlet. Use one of the following cmdlets:



- Add-CMDeviceCollectionDirectMembershipRule (Add-CMDeviceCollectionDirectMembershipRule.md)- Add-CMDeviceCollectionExcludeMembershipRule (Add-CMDeviceCollectionExcludeMembershipRule.md)- Add-CMDeviceCollectionIncludeMembershipRule (Add-CMDeviceCollectionIncludeMembershipRule.md)- Add-CMDeviceCollectionQueryMembershipRule (Add-CMDeviceCollectionQueryMembershipRule.md)- Add-CMUserCollectionDirectMembershipRule (Add-CMUserCollectionDirectMembershipRule.md)- Add-CMUserCollectionExcludeMembershipRule (Add-CMUserCollectionExcludeMembershipRule.md)- Add-CMUserCollectionIncludeMembershipRule (Add-CMUserCollectionIncludeMembershipRule.md)- Add-CMUserCollectionQueryMembershipRule (Add-CMUserCollectionQueryMembershipRule.md)



---


### Parameters
#### **ChildSearchCriteria**








|Type                 |Required|Position|PipelineInput|Aliases       |
|---------------------|--------|--------|-------------|--------------|
|`[SmsProviderSearch]`|true    |named   |False        |SearchCriteria|



#### **CollectionId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionType**





Valid Values:

* Root
* User
* Device
* Unknown






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[CollectionType]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExtraArguments**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RuleClassName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RulePropertyName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
System.Object



Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Add-CMCollectionMembershipRule -ChildSearchCriteria <SmsProviderSearch> -CollectionId <String> -CollectionType {User | Device} [-DisableWildcardHandling] [-ExtraArguments <Object>] [-ForceWildcardHandling] [-PassThru] -RuleClassName <String> -RulePropertyName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMCollectionMembershipRule -ChildSearchCriteria <SmsProviderSearch> -CollectionName <String> -CollectionType {User | Device} [-DisableWildcardHandling] [-ExtraArguments <Object>] [-ForceWildcardHandling] [-PassThru] -RuleClassName <String> -RulePropertyName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMCollectionMembershipRule -ChildSearchCriteria <SmsProviderSearch> -CollectionType {User | Device} [-DisableWildcardHandling] [-ExtraArguments <Object>] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] -RuleClassName <String> -RulePropertyName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
