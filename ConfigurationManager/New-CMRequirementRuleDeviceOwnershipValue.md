New-CMRequirementRuleDeviceOwnershipValue
-----------------------------------------




### Synopsis
Create a device ownership requirement rule for an application deployment type.



---


### Description

Use this cmdlet to create a device ownership requirement rule for an application deployment type. The Ownership default global condition determines whether the device is Personal or Company owned.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this requirement rule object to either the AddRequirement or RemoveRequirement parameters.



For more information, see Deployment type Requirements (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-require) and [Create global conditions](/mem/configmgr/apps/deploy-use/create-global-conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMRequirementRuleActiveDirectorySiteValue](New-CMRequirementRuleActiveDirectorySiteValue)



* [New-CMRequirementRuleBooleanValue](New-CMRequirementRuleBooleanValue)



* [New-CMRequirementRuleCMSiteValue](New-CMRequirementRuleCMSiteValue)



* [New-CMRequirementRuleCommonValue](New-CMRequirementRuleCommonValue)



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
#### Example 1: Add a requirement rule for device ownership
```PowerShell
$gc = Get-CMGlobalCondition -Name "Configuration Manager site"
$sites = @('XYZ', 'ABC')
$rule = New-CMRequirementRuleActiveDirectorySiteValue -InputObject $gc -RuleOperator IsEquals -OwnershipOption Company

Set-CMScriptDeploymentType -ApplicationName "Central App" -DeploymentTypeName "Install" -AddRequirement $rule
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


In most instances, you'll use the default Ownership global condition, for example: `Get-CMGlobalCondition -Name "Ownership"`.






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |0       |True (ByValue)|GlobalCondition|



#### **OwnershipOption**

Specify the device ownership type to compare against the device's configuration.



Valid Values:

* Personal
* Company






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[OwnershipType]`|true    |named   |False        |



#### **RuleOperator**

Specify the operator to compare the device's setting with the OwnershipOption .



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
New-CMRequirementRuleDeviceOwnershipValue [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -OwnershipOption {Personal | Company} -RuleOperator {IsEquals | NotEquals} [<CommonParameters>]
```
