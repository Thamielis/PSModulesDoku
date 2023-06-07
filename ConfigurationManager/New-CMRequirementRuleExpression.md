New-CMRequirementRuleExpression
-------------------------------




### Synopsis
Create a requirement rule to evaluate a custom global condition with a complex expression.



---


### Description

Use this cmdlet to create a requirement rule on an application deployment type that evaluates a custom global condition with a complex expression. When you create a global condition, the Condition type needs to be Expression . These expressions let you add multiple clauses and group them with logical operators.



To create a custom global condition with an expression, use the New-CMGlobalConditionExpression (New-CMGlobalConditionExpression.md)cmdlet.



After you use the New-CMRequirementRuleExpression cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this requirement rule object to either the AddRequirement or RemoveRequirement parameters.



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



* [New-CMGlobalConditionExpression](New-CMGlobalConditionExpression)



* [Deployment type Requirements](Deployment type Requirements)



* [Create global conditions](Create global conditions)





---


### Examples
#### Example 1: Add a basic expression
```PowerShell
$rule1 = Get-CMGlobalCondition -Name "Total physical memory" | New-CMRequirementRuleCommonValue -Value1 2048 -RuleOperator GreaterEquals
$myRuleExpression = New-CMRequirementRuleExpression -AddRequirementRule $rule1
$myGC = New-CMGlobalConditionExpression -Name "GCExp" -DeviceType Windows -RootExpression $myRuleExpression
```

#### Example 2: Add a complex global condition expression
```PowerShell
$ruleProc = Get-CMGlobalCondition -Name "Number of processors" | New-CMRequirementRuleCommonValue -Value1 2 -RuleOperator GreaterEquals
$ruleMem1 = Get-CMGlobalCondition -Name "Total physical memory" | New-CMRequirementRuleCommonValue -Value1 2048 -RuleOperator GreaterThan
$ruleMem2 = Get-CMGlobalCondition -Name "Total physical memory" | New-CMRequirementRuleCommonValue -Value1 4096 -RuleOperator LessEquals
$ruleCPUSpeed1 = Get-CMGlobalCondition -Name "CPU Speed" | New-CMRequirementRuleCommonValue -Value1 5120 -RuleOperator LessEquals
$ruleCPUSpeed2 = Get-CMGlobalCondition -Name "CPU Speed" | New-CMRequirementRuleCommonValue -Value1 1024 -RuleOperator GreaterThan
$expressionProc = New-CMRequirementRuleExpression -AddRequirementRule $ruleProc
$expressionMem = New-CMRequirementRuleExpression -AddRequirementRule $ruleMem1, $ruleMem2 -ClauseOperator And
$expressionCPU = New-CMRequirementRuleExpression -AddRequirementRule $ruleCPUSpeed1, $ruleCPUSpeed2 -ClauseOperator And
$myRuleExpression = New-CMRequirementRuleExpression -RootExpression $expressionProc -AddExpression $expressionMem,$expressionCPU -ClauseOperator And -AddAsGroup -GroupOperator Or
$myGC = New-CMGlobalConditionExpression -Name "GCExp" -DeviceType Windows -RootExpression $myRuleExpression
```



---


### Parameters
#### **AddAsGroup**

Add this parameter to add the expressions as a group. Specify more than one expression with the AddExpression parameter. Use the GroupOperator parameter to specify the connector.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **AddExpression**

Specify one or more expression objects to add to a new expression. Create these objects with this same cmdlet. Use the RootExpression parameter to specify the first expression.






|Type                |Required|Position|PipelineInput|Aliases       |
|--------------------|--------|--------|-------------|--------------|
|`[ExpressionBase[]]`|false   |named   |False        |AddExpressions|



#### **AddRequirementRule**

Specify an array of requirement objects for the expression. To create a requirement rule object, use one of the following cmdlets:


* New-CMRequirementRuleActiveDirectorySiteValue (New-CMRequirementRuleActiveDirectorySiteValue.md)- New-CMRequirementRuleBooleanValue (New-CMRequirementRuleBooleanValue.md)- New-CMRequirementRuleCMSiteValue (New-CMRequirementRuleCMSiteValue.md)- New-CMRequirementRuleCommonValue (New-CMRequirementRuleCommonValue.md)- New-CMRequirementRuleDeviceOwnershipValue (New-CMRequirementRuleDeviceOwnershipValue.md)- New-CMRequirementRuleExistential (New-CMRequirementRuleExistential.md)- New-CMRequirementRuleExpression (New-CMRequirementRuleExpression.md)- New-CMRequirementRuleFileAttributeValue (New-CMRequirementRuleFileAttributeValue.md)- New-CMRequirementRuleFilePermissionValue (New-CMRequirementRuleFilePermissionValue.md)- New-CMRequirementRuleFreeDiskSpaceValue (New-CMRequirementRuleFreeDiskSpaceValue.md)- New-CMRequirementRuleInputTypeValue (New-CMRequirementRuleInputTypeValue.md)- New-CMRequirementRuleOperatingSystemLanguageValue (New-CMRequirementRuleOperatingSystemLanguageValue.md)- New-CMRequirementRuleOperatingSystemValue (New-CMRequirementRuleOperatingSystemValue.md)- New-CMRequirementRuleOUValue (New-CMRequirementRuleOUValue.md)- New-CMRequirementRuleRegistryKeyPermissionValue (New-CMRequirementRuleRegistryKeyPermissionValue.md)- New-CMRequirementRuleScreenResolutionValue (New-CMRequirementRuleScreenResolutionValue.md)






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[Rule[]]`|false   |named   |False        |AddRequirementRules|



#### **ClauseOperator**

Specify the logical operator to use as the connector between multiple expressions.



Valid Values:

* None
* Or
* And






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[ConnectOperator]`|false   |named   |False        |



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



#### **GroupOperator**

Specify the logical operator to use as the connector between groups. Use this parameter with the AddAsGroup parameter.



Valid Values:

* None
* Or
* And






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[ConnectOperator]`|false   |named   |False        |



#### **RootExpression**

Specify the first expression with this parameter. Create an expression object with this same cmdlet. To add more than one expression, also use the AddExpression parameter.






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[ExpressionBase]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMRequirementRuleExpression [-AddAsGroup] [-AddExpression <ExpressionBase[]>] [-AddRequirementRule <Rule[]>] [-ClauseOperator {And | Or}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-GroupOperator {And | Or}] [-RootExpression <ExpressionBase>] [<CommonParameters>]
```
