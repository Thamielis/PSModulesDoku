New-CMRequirementRuleCommonValue
--------------------------------




### Synopsis
Create a requirement rule to evaluate a value-based global condition on an application deployment type.



---


### Description

Use this cmdlet to create a requirement rule on an application deployment type that evaluates a global condition with a Value rule type.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this requirement rule object to either the AddRequirement or RemoveRequirement parameters.



For more information, see Deployment type Requirements (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-require) and [Create global conditions](/mem/configmgr/apps/deploy-use/create-global-conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMRequirementRuleActiveDirectorySiteValue](New-CMRequirementRuleActiveDirectorySiteValue)



* [New-CMRequirementRuleBooleanValue](New-CMRequirementRuleBooleanValue)



* [New-CMRequirementRuleCMSiteValue](New-CMRequirementRuleCMSiteValue)



* [New-CMRequirementRuleDeviceOwnershipValue](New-CMRequirementRuleDeviceOwnershipValue)



* [New-CMRequirementRuleExistential](New-CMRequirementRuleExistential)



* [New-CMRequirementRuleExpression](New-CMRequirementRuleExpression)



* [New-CMRequirementRuleFileAttributeValue](New-CMRequirementRuleFileAttributeValue)



* [New-CMRequirementRuleFilePermissionValue](New-CMRequirementRuleFilePermissionValue)



* [New-CMRequirementRuleFreeDiskSpaceValue](New-CMRequirementRuleFreeDiskSpaceValue)



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
#### Example 1: Add a requirement rule for number of processors
```PowerShell
$myGC = Get-CMGlobalCondition -Name "Number of processors"
$myRule = New-CMRequirementRuleCommonValue -GlobalCondition $myGC -Value1 "2" -RuleOperator GreaterEquals

Set-CMScriptDeploymentType -ApplicationName "Central app" -DeploymentTypeName "Install" -AddRequirement $myRule
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



#### **InputObject**

Specify a global condition object to use as the basis for this requirement rule. To get this object, use the Get-CMGlobalCondition (Get-CMGlobalCondition.md)cmdlet.


The global condition needs to support the Rule type of Value .






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |0       |True (ByValue)|GlobalCondition|



#### **PropertyForAssembly**

If the global condition supports it, specify the assembly property to compare with the expected value.



Valid Values:

* Culture
* Version
* PublicKeyToken






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[AssemblyProperty]`|false   |named   |False        |



#### **PropertyForFileFolder**

If the global condition supports it, specify a file or folder property to compare with the expected value.


For example:


`$myRule = New-CMRequirementRuleCommonValue -GlobalCondition $myGC -PropertyForFileFolder DateCreated -Value1 "2018-08-07T05:32:45Z" -RuleOperator GreaterEquals`



Valid Values:

* Size
* Version
* DateCreated
* DateModified
* Company
* ProductName
* SHA1Hash
* Permissions
* Attributes






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[FileFolderProperty]`|false   |named   |False        |



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

Specify a string or array of expected values to compare.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **Value2**

If you use a RuleOperator like `Between`, use this parameter to specify the upper value.


For example:






$myRule = New-CMRequirementRuleCommonValue -GlobalCondition $GC -PropertyForFileFolder Size -Value1 200 -Value2 300 -RuleOperator Between







|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |





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
New-CMRequirementRuleCommonValue [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PropertyForAssembly {Culture | Version | PublicKeyToken}] [-PropertyForFileFolder {Size | Version | DateCreated | DateModified | Company | ProductName | SHA1Hash | Permissions | Attributes}] -RuleOperator {And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll} -Value1 <String[]> [-Value2 <String[]>] [<CommonParameters>]
```
