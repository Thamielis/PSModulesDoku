Remove-CMCollectionMembershipRule
---------------------------------




### Synopsis
For system use only to remove membership rules from collections.



---


### Description

This cmdlet is used by other cmdlets to get membership rules. Don't directly use this cmdlet. Use one of the following cmdlets:



- Remove-CMCollectionDirectMembershipRule (Remove-CMCollectionDirectMembershipRule.md)- Remove-CMCollectionExcludeMembershipRule (Remove-CMCollectionExcludeMembershipRule.md)- Remove-CMCollectionIncludeMembershipRule (Remove-CMCollectionIncludeMembershipRule.md)- Remove-CMCollectionQueryMembershipRule (Remove-CMCollectionQueryMembershipRule.md)



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

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExtraArguments**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






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
Remove-CMCollectionMembershipRule -ChildSearchCriteria <SmsProviderSearch> -CollectionId <String> [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ExtraArguments <Object>] [-Force] [-ForceWildcardHandling] -RuleClassName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionMembershipRule -ChildSearchCriteria <SmsProviderSearch> -CollectionName <String> [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ExtraArguments <Object>] [-Force] [-ForceWildcardHandling] -RuleClassName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionMembershipRule -ChildSearchCriteria <SmsProviderSearch> [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ExtraArguments <Object>] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> -RuleClassName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
