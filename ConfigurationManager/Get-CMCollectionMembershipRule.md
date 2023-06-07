Get-CMCollectionMembershipRule
------------------------------




### Synopsis
For system use only to get membership rules from collections.



---


### Description

This cmdlet is used by other cmdlets to get membership rules. Don't directly use this cmdlet. Use one of the following cmdlets:



- Get-CMCollectionDirectMembershipRule (Get-CMCollectionDirectMembershipRule.md)- Get-CMCollectionExcludeMembershipRule (Get-CMCollectionExcludeMembershipRule.md)- Get-CMCollectionIncludeMembershipRule (Get-CMCollectionIncludeMembershipRule.md)- Get-CMCollectionQueryMembershipRule (Get-CMCollectionQueryMembershipRule.md)



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
|`[CollectionType]`|false   |named   |False        |



#### **DisableWildcardHandling**

DisableWildcardHandling treats wildcard characters as literal character values. Can't be combined with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExtraArguments**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |named   |False        |



#### **ForceWildcardHandling**

ForceWildcardHandling processes wildcard characters and may lead to unexpected behavior (not recommended). Can't be combined with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **RuleClassName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





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
Get-CMCollectionMembershipRule -ChildSearchCriteria <SmsProviderSearch> -CollectionId <String> [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ExtraArguments <Object>] [-ForceWildcardHandling] -RuleClassName <String> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionMembershipRule -ChildSearchCriteria <SmsProviderSearch> -CollectionName <String> [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ExtraArguments <Object>] [-ForceWildcardHandling] -RuleClassName <String> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionMembershipRule -ChildSearchCriteria <SmsProviderSearch> [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ExtraArguments <Object>] [-ForceWildcardHandling] -InputObject <IResultObject> -RuleClassName <String> [<CommonParameters>]
```
