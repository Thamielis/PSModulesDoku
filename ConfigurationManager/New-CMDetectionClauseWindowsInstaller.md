New-CMDetectionClauseWindowsInstaller
-------------------------------------




### Synopsis
Create a detection method clause for an MSI product code.



---


### Description

Use this cmdlet to create a clause in a detection method on an application. This clause is a rule for a Windows Installer (MSI) product code that indicates the presence of an application.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this detection clause object to either the AddDetectionClause or RemoveDetectionClause parameters.



To group detection clauses, use the GroupDetectionClauses parameter on the deployment type cmdlets.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDetectionClauseDirectory](New-CMDetectionClauseDirectory)



* [New-CMDetectionClauseFile](New-CMDetectionClauseFile)



* [New-CMDetectionClauseRegistryKey](New-CMDetectionClauseRegistryKey)



* [New-CMDetectionClauseRegistryKeyValue](New-CMDetectionClauseRegistryKeyValue)





---


### Examples
#### Example 1: Detect the existence of an MSI product code
```PowerShell
$clause = New-CMDetectionClauseWindowsInstaller -Existence -ProductCode 4F7840A9-9816-45E2-9F6C-F7067A8BC0FD

Set-CMScriptDeploymentType -ApplicationName "Configuration Manager console" -DeploymentTypeName "Install" -AddDetectionClause $clause
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Existence**

When you add this parameter, the MSI product code must exist on the target system to indicate presence of this application.


Instead of just existence, to also evaluate a version condition, use the Value parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ExpectedValue**

When you add the Value parameter, use ExpectedValue with PropertyType and ExpressionOperator . When you use these parameters, the MSI version must satisfy the rule to indicate the presence of this application. This ExpectedValue parameter specifies the value to compare against the device.


<!-- The value to compare depends upon the specified PropertyType . -->






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ExpressionOperator**

When you add the Value parameter, use ExpressionOperator with PropertyType and ExpectedValue . When you use these parameters, the MSI version must satisfy the rule to indicate the presence of this application. This ExpressionOperator parameter specifies the operator to compare the device's value with the expected value.


Starting in version 2010, the parameter type changed from RuleExpressionOperator to WindowsInstallerRuleExpressionOperator .



Valid Values:

* IsEquals
* NotEquals
* GreaterThan
* LessThan
* GreaterEquals
* LessEquals






|Type                                      |Required|Position|PipelineInput|
|------------------------------------------|--------|--------|-------------|
|`[WindowsInstallerRuleExpressionOperator]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ProductCode**

Specify the Windows Installer product code that indicates the presence of this application. The format is a GUID, for example `4F7840A9-9816-45E2-9F6C-F7067A8BC0FD`.






|Type    |Required|Position|PipelineInput|
|--------|--------|--------|-------------|
|`[Guid]`|true    |named   |False        |



#### **PropertyType**

When you add the Value parameter, use PropertyType with ExpressionOperator and ExpectedValue . When you use these parameters, the MSI version must satisfy the rule to indicate the presence of this application.


This PropertyType parameter currently only supports a single value, `ProductVersion`.



Valid Values:

* ProductVersion
* UpgradeCode






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[MSIProperty]`|false   |named   |False        |



#### **Value**

When you add the Value parameter, along with the product code, the MSI version must also satisfy the rule to indicate the presence of this application. Use this parameter with the following parameters: ExpectedValue , ExpressionOperator , and PropertyType .


Instead of evaluating a rule, to just check the MSI product code, use the Existence parameter.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[Switch]`|true    |named   |False        |ValueRule|





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
New-CMDetectionClauseWindowsInstaller [-DisableWildcardHandling] -Existence [-ForceWildcardHandling] -ProductCode <Guid> [<CommonParameters>]
```
```PowerShell
New-CMDetectionClauseWindowsInstaller [-DisableWildcardHandling] -ExpectedValue <String> -ExpressionOperator {IsEquals | NotEquals | GreaterThan | LessThan | GreaterEquals | LessEquals} [-ForceWildcardHandling] -ProductCode <Guid> [-PropertyType {ProductVersion}] -Value [<CommonParameters>]
```
