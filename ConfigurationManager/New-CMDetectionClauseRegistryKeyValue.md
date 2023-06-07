New-CMDetectionClauseRegistryKeyValue
-------------------------------------




### Synopsis
Create a detection method clause for a registry key value.



---


### Description

Use this cmdlet to create a clause in a detection method on an application. This clause is a rule for a registry key value to indicate the presence of an application.



To detect the existence of a registry key instead of a value, use the New-CMDetectionClauseRegistryKey (New-CMDetectionClauseRegistryKey.md)cmdlet.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this detection clause object to either the AddDetectionClause or RemoveDetectionClause parameters.



To group detection clauses, use the GroupDetectionClauses parameter on the deployment type cmdlets.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDetectionClauseDirectory](New-CMDetectionClauseDirectory)



* [New-CMDetectionClauseFile](New-CMDetectionClauseFile)



* [New-CMDetectionClauseRegistryKey](New-CMDetectionClauseRegistryKey)



* [New-CMDetectionClauseWindowsInstaller](New-CMDetectionClauseWindowsInstaller)





---


### Examples
#### Example 1: Detect the existence of a registry value
```PowerShell
$regClause = New-CMDetectionClauseRegistryKeyValue -Hive LocalMachine -KeyName "SOFTWARE\GitForWindows" -PropertyType String -ValueName "CurrentVersion" -Existence

Set-CMMsiDeploymentType -ApplicationName "Git for Windows" -DeploymentTypeName "Install" -AddDetectionClause $regClause
```

#### Example 2: Compare a version value in the registry
```PowerShell
$clause = New-CMDetectionClauseRegistryKeyValue -Hive LocalMachine -KeyName 'Software\Microsoft\Office\ClickToRun\Configuration' -PropertyType Version -ValueName 'VersionToReport' -Value -ExpectedValue '16.0.10730.20304' -ExpressionOperator GreaterEquals

Set-CMMsiDeploymentType -ApplicationName "Microsoft 365" -DeploymentTypeName "Install" -AddDetectionClause $clause
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Existence**

When you add this parameter, the registry key value must exist on the target system to indicate presence of this application.


Instead of just existence, to evaluate a rule for the data of this registry key value, use the Value parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ExpectedValue**

When you add the Value parameter, use ExpectedValue with PropertyType and ExpressionOperator . When you use these parameters, the registry key value must satisfy the rule to indicate the presence of this application. This ExpectedValue parameter specifies the value to compare against the registry key value.


The value to compare depends upon the specified PropertyType .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **ExpressionOperator**

When you add the Value parameter, use ExpressionOperator with PropertyType and ExpectedValue . When you use these parameters, the registry key value must satisfy the rule to indicate the presence of this application. This ExpressionOperator parameter specifies the operator to compare the registry key value with the expected value.


Starting in version 2010, the parameter type changed from RuleExpressionOperator to RegistryValueRuleExpressionOperator .



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
* BeginsWith
* NotBeginsWith
* EndsWith
* NotEndsWith
* Contains
* NotContains






|Type                                   |Required|Position|PipelineInput|
|---------------------------------------|--------|--------|-------------|
|`[RegistryValueRuleExpressionOperator]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Hive**

Specify the registry hive where the key exists. Use the KeyName parameter to specify the key name. Use the ValueName parameter to specify the registry key value.


For example, the following PowerShell command translates to the following parameter values:


`Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' | Select-Object CurrentVersion`


|Parameter|Value| |---------|---------| | Hive |`LocalMachine`| | KeyName |`'SOFTWARE\Microsoft\Windows NT\CurrentVersion'`| | ValueName |`CurrentVersion`|



Valid Values:

* ClassesRoot
* CurrentConfig
* CurrentUser
* LocalMachine
* Users






|Type               |Required|Position|PipelineInput|Aliases     |
|-------------------|--------|--------|-------------|------------|
|`[RegistryRootKey]`|true    |named   |False        |RegistryHive|



#### **Is64Bit**

Add this parameter to indicate that this registry key is associated with a 32-bit application on 64-bit systems.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **KeyName**

Specify the name of the registry key that must exist to indicate the presence of this application. Use the Hive parameter to specify the registry hive where this key should exist. Use the ValueName parameter to specify the registry key value.


For example, the following PowerShell command translates to the following parameter values:






Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' | Select-Object CurrentVersion


|Parameter|Value| |---------|---------| | Hive |`LocalMachine`| | KeyName |`'SOFTWARE\Microsoft\Windows NT\CurrentVersion'`| | ValueName |`CurrentVersion`|







|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |RegistryKey|



#### **PropertyType**

When you add the Value parameter, use PropertyType with ExpressionOperator and ExpectedValue . When you use these parameters, the registry key value must satisfy the rule to indicate the presence of this application. This PropertyType parameter specifies the data type of the registry key value.


For example, you set this parameter to `Version`, set ExpressionOperator to `IsEquals`, and ExpectedValue to `1.48.1.0`. The rule then checks the specified registry key value to have that same version.



Valid Values:

* String
* Integer
* DateTime
* FloatingPoint
* Version
* StringArray
* Boolean
* IntegerArray






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[SettingDataType]`|true    |named   |False        |



#### **Value**

When you add the Value parameter, the registry key value must satisfy the rule to indicate the presence of this application. Use this parameter with the following parameters: ExpectedValue , ExpressionOperator , and PropertyType .


Instead of evaluating a rule, to just check that the registry key value exists, use the Existence parameter.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[Switch]`|true    |named   |False        |ValueRule|



#### **ValueName**

Specify the registry key value that indicates the presence of the application. Use the Hive parameter to specify the registry hive, and KeyName to specify the registry key.


For example, the following PowerShell command translates to the following parameter values:






Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' | Select-Object CurrentVersion


|Parameter|Value| |---------|---------| | Hive |`LocalMachine`| | KeyName |`'SOFTWARE\Microsoft\Windows NT\CurrentVersion'`| | ValueName |`CurrentVersion`|







|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|true    |named   |False        |RegistryValueName|





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
New-CMDetectionClauseRegistryKeyValue [-DisableWildcardHandling] -Existence [-ForceWildcardHandling] -Hive {ClassesRoot | CurrentConfig | CurrentUser | LocalMachine | Users} [-Is64Bit] -KeyName <String> -PropertyType {Version | Integer | String} -ValueName <String> [<CommonParameters>]
```
```PowerShell
New-CMDetectionClauseRegistryKeyValue [-DisableWildcardHandling] -ExpectedValue <String[]> -ExpressionOperator {IsEquals | NotEquals | GreaterThan | LessThan | Between | GreaterEquals | LessEquals | OneOf | NoneOf | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains} [-ForceWildcardHandling] -Hive {ClassesRoot | CurrentConfig | CurrentUser | LocalMachine | Users} [-Is64Bit] -KeyName <String> -PropertyType {Version | Integer | String} -Value -ValueName <String> [<CommonParameters>]
```
