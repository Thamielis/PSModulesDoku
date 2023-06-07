New-CMDetectionClauseDirectory
------------------------------




### Synopsis
Create a detection method clause for a file system directory.



---


### Description

Use this cmdlet to create a clause in a detection method on an application. This clause is a rule for a file system folder that indicates the presence of an application.



To detect a file instead of a folder, use the New-CMDetectionClauseFile (New-CMDetectionClauseFile.md)cmdlet.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this detection clause object to either the AddDetectionClause or RemoveDetectionClause parameters.



To group detection clauses, use the GroupDetectionClauses parameter on the deployment type cmdlets.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDetectionClauseFile](New-CMDetectionClauseFile)



* [New-CMDetectionClauseRegistryKey](New-CMDetectionClauseRegistryKey)



* [New-CMDetectionClauseRegistryKeyValue](New-CMDetectionClauseRegistryKeyValue)



* [New-CMDetectionClauseWindowsInstaller](New-CMDetectionClauseWindowsInstaller)





---


### Examples
#### Example 1: Add an existence detection method
```PowerShell
$app = Get-CMApplication -ApplicationName "CentralApp"
$guid = "9900a338-484b-4a18-884e-bce87654ce1b"
$clause1 = New-CMDetectionClauseWindowsInstaller -ProductCode $guid -Value -ExpressionOperator IsEquals -ExpectedValue "1.1.1.1"
$clause2 = New-CMDetectionClauseDirectory -DirectoryName "mymsi" -Path "C:\" -Existence

$app | Add-CMMsiDeploymentType -ContentLocation "\\myserver\mypath\mymsi.msi" -Force -AddDetectionClause ($clause1, $clause2)
```

#### Example 2: Add a rule evaluation detection method
```PowerShell
$clause1 = New-CMDetectionClauseDirectory -DirectoryName "AdminConsole" -Path "%ProgramFiles(x86)%\Microsoft Endpoint Manager" -Value -PropertyType DateCreated -ExpressionOperator GreaterThan -ExpectedValue "2020-11-30T08:00:00Z"

Set-CMScriptDeploymentType -ApplicationName "Configuration Manager console" -DeploymentTypeName "Install" -AddDetectionClause $clause1
```



---


### Parameters
#### **DirectoryName**

Specify the name of the folder that indicates the presence of the application. Use the Path parameter to specify the path to this folder.


For example, the Configuration Manager console installs by default to `C:\Program Files (x86)\Microsoft Endpoint Manager\AdminConsole`. To create a rule for this folder, set this parameter to `AdminConsole` and the Path parameter to `%ProgramFiles(x86)%\Microsoft Endpoint Manager`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Existence**

When you add this parameter, the folder must exist on the target system to indicate presence of this application.


Instead of just existence, to evaluate a rule for properties of this folder, use the Value parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ExpectedValue**

When you add the Value parameter, use ExpectedValue with PropertyType and ExpressionOperator . When you use these parameters, the folder must satisfy the rule to indicate the presence of this application. This ExpectedValue parameter specifies the value to compare against the file system.


The PropertyType parameter for this clause only accepts the date the folder was created or modified, so this value is a string with a valid datetime. For example, `"2020-11-30T08:00:00Z"`.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **ExpressionOperator**

When you add the Value parameter, use ExpressionOperator with PropertyType and ExpectedValue . When you use these parameters, the folder must satisfy the rule to indicate the presence of this application. This ExpressionOperator parameter specifies the operator to compare the file system value with the expected value.


Starting in version 2010, the parameter type changed from RuleExpressionOperator to FileFolderRuleExpressionOperator .



Valid Values:

* IsEquals
* NotEquals
* GreaterThan
* LessThan
* Between
* GreaterEquals
* LessEquals
* OneOf
* NoneOf






|Type                                |Required|Position|PipelineInput|
|------------------------------------|--------|--------|-------------|
|`[FileFolderRuleExpressionOperator]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Is64Bit**

Add this parameter to indicate that this folder is associated with a 32-bit application on 64-bit systems.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

Specify the path in the file system to the folder that indicates the presence of the application. Use the DirectoryName parameter to specify the name of the folder.


For example, the Configuration Manager console installs by default to `C:\Program Files (x86)\Microsoft Endpoint Manager\AdminConsole`. To create a rule for this folder, set this parameter to `%ProgramFiles(x86)%\Microsoft Endpoint Manager` and the DirectoryName parameter to `AdminConsole`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PropertyType**

When you add the Value parameter, use PropertyType with ExpressionOperator and ExpectedValue . When you use these parameters, the folder must satisfy the rule to indicate the presence of this application. This PropertyType parameter specifies the folder property to evaluate.



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
|`[FileFolderProperty]`|true    |named   |False        |



#### **Value**

When you add the Value parameter, the folder must satisfy the rule to indicate the presence of this application. Use this parameter with the following parameters: ExpectedValue , ExpressionOperator , and PropertyType .


Instead of evaluating a rule, to just check that the folder exists, use the Existence parameter.






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
New-CMDetectionClauseDirectory -DirectoryName <String> [-DisableWildcardHandling] -Existence [-ForceWildcardHandling] [-Is64Bit] -Path <String> [<CommonParameters>]
```
```PowerShell
New-CMDetectionClauseDirectory -DirectoryName <String> [-DisableWildcardHandling] -ExpectedValue <String[]> -ExpressionOperator {IsEquals | NotEquals | GreaterThan | LessThan | Between | GreaterEquals | LessEquals | OneOf | NoneOf} [-ForceWildcardHandling] [-Is64Bit] -Path <String> -PropertyType {DateCreated | DateModified} -Value [<CommonParameters>]
```
