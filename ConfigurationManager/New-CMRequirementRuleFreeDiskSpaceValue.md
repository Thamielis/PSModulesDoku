New-CMRequirementRuleFreeDiskSpaceValue
---------------------------------------




### Synopsis
Create a disk space requirement rule for an application deployment type.



---


### Description

Use this cmdlet to create a disk space requirement rule for an application deployment type.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this requirement rule object to either the AddRequirement or RemoveRequirement parameters.



For more information, see Deployment type Requirements (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-require) and [Create global conditions](/mem/configmgr/apps/deploy-use/create-global-conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMRequirementRuleActiveDirectorySiteValue](New-CMRequirementRuleActiveDirectorySiteValue)



* [New-CMRequirementRuleBooleanValue](New-CMRequirementRuleBooleanValue)



* [New-CMRequirementRuleCMSiteValue](New-CMRequirementRuleCMSiteValue)



* [New-CMRequirementRuleCommonValue](New-CMRequirementRuleCommonValue)



* [New-CMRequirementRuleDeviceOwnershipValue](New-CMRequirementRuleDeviceOwnershipValue)



* [New-CMRequirementRuleExistential](New-CMRequirementRuleExistential)



* [New-CMRequirementRuleExpression](New-CMRequirementRuleExpression)



* [New-CMRequirementRuleFileAttributeValue](New-CMRequirementRuleFileAttributeValue)



* [New-CMRequirementRuleFilePermissionValue](New-CMRequirementRuleFilePermissionValue)



* [New-CMRequirementRuleInputTypeValue](New-CMRequirementRuleInputTypeValue)



* [New-CMRequirementRuleOperatingSystemLanguageValue](New-CMRequirementRuleOperatingSystemLanguageValue)



* [New-CMRequirementRuleOperatingSystemValue](New-CMRequirementRuleOperatingSystemValue)



* [New-CMRequirementRuleOUValue](New-CMRequirementRuleOUValue)



* [New-CMRequirementRuleRegistryKeyPermissionValue](New-CMRequirementRuleRegistryKeyPermissionValue)



* [New-CMRequirementRuleScreenResolutionValue](New-CMRequirementRuleScreenResolutionValue)



* [Get-CMGlobalCondition](Get-CMGlobalCondition)



* [Deployment type Requirements](Deployment type Requirements)



* [Create global conditions](Create global conditions)





---


### Examples
#### Example 1: Add a requirement rule for disk space
```PowerShell
$value1 = 5

$value2 = 10

$myGC = Get-CMGlobalCondition -Name "Disk space"

$myRule = $myGC | New-CMRequirementRuleFreeDiskSpaceValue -PartitionOption Special -RuleOperator Between -Value1 $value1 -Value2 $value2 -DriverLetter "E:"

Set-CMScriptDeploymentType -ApplicationName "Central App" -DeploymentTypeName "Install" -AddRequirement $myRule
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DriverLetter**

When you set the PartitionOption parameter to `Special`, use this parameter to specify the drive letter. For example, `"C:"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a global condition object to use as the basis for this requirement rule. To get this object, use the Get-CMGlobalCondition (Get-CMGlobalCondition.md)cmdlet.


In most instances, you'll use the default Disk space global condition, for example: `Get-CMGlobalCondition -Name "Disk space"`.






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |0       |True (ByValue)|GlobalCondition|



#### **PartitionOption**

Specify the type of partition to evaluate with this requirement rule:


* `Any`: Any drive on the device


* `System`: The Windows system drive


* `Special`: A specific drive. Use the DriverLetter parameter to specify the drive letter.



Valid Values:

* Any
* System
* Special






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[PartitionType]`|true    |named   |False        |



#### **RuleOperator**

Specify the operator to compare the device's setting with the expected value.



Valid Values:

* And
* Or
* Other
* IsEquals
* NotEquals
* GreaterThan
* LessThan
* Between
* NotBetween
* GreaterEquals
* LessEquals
* BeginsWith
* NotBeginsWith
* EndsWith
* NotEndsWith
* Contains
* NotContains
* AllOf
* OneOf
* NoneOf
* SetEquals
* SubsetOf
* ExcludesAll






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[RuleExpressionOperator]`|true    |named   |False        |



#### **Value1**

Specify an integer or array of expected values to compare. This value is the amount of free space in megabytes (MB).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Int64[]]`|true    |named   |False        |



#### **Value2**

If you use a RuleOperator like `Between`, use this parameter to specify the upper value.


For example:


`$myRule = New-CMRequirementRuleFreeDiskSpaceValue -InputObject $GC -PartitionOption System -RuleOperator Between -Value1 1024 -Value2 2048`






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int64]`|false   |named   |False        |





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
New-CMRequirementRuleFreeDiskSpaceValue [-InputObject] <IResultObject> [-DisableWildcardHandling] [-DriverLetter <String>] [-ForceWildcardHandling] -PartitionOption {Any | System | Special} -RuleOperator {IsEquals | NotEquals | GreaterThan | GreaterEquals | LessThan | LessEquals | Between} -Value1 <Int64[]> [-Value2 <Int64>] [<CommonParameters>]
```
