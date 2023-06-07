New-CMDetectionClauseRegistryKey
--------------------------------




### Synopsis
Create a detection method clause for a registry key.



---


### Description

Use this cmdlet to create a clause in a detection method on an application. This clause is a rule for a registry key to indicate the presence of an application.



To detect a registry value instead of a key, use the New-CMDetectionClauseRegistryKeyValue (New-CMDetectionClauseRegistryKeyValue.md)cmdlet.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this detection clause object to either the AddDetectionClause or RemoveDetectionClause parameters.



To group detection clauses, use the GroupDetectionClauses parameter on the deployment type cmdlets.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDetectionClauseDirectory](New-CMDetectionClauseDirectory)



* [New-CMDetectionClauseFile](New-CMDetectionClauseFile)



* [New-CMDetectionClauseRegistryKeyValue](New-CMDetectionClauseRegistryKeyValue)



* [New-CMDetectionClauseWindowsInstaller](New-CMDetectionClauseWindowsInstaller)





---


### Examples
#### Example 1: Create multiple clauses for an MSI app deployment type
```PowerShell
$cla1=New-CMDetectionClauseFile -FileName "filetest" -PropertyType Size -ExpectedValue 123 -ExpressionOperator IsEquals -Path "C:\" -Value -Is64Bit
$cla2=New-CMDetectionClauseFile -FileName "foldertest" -PropertyType DateCreated -ExpectedValue (Get-Date) -ExpressionOperator LessThan -Path "C:\" -Value
$cla3=New-CMDetectionClauseRegistryKey -Hive ClassesRoot -KeyName "aaa"
$logic1=$cla1.Setting.LogicalName
$logic2=$cla2.Setting.LogicalName
$logic3=$cla3.Setting.LogicalName

Add-CMMsiDeploymentType -AddDetectionClause $cla1,$cla2,$cla3 -ApplicationName "app" -DeploymentTypeName "dt" -InstallCommand "mycommand" -ContentLocation "\\server\sources\Orca.msi" -GroupDetectionClauses $logic1,$logic2 -DetectionClauseConnector {LogicalName=$logic2;Connector="or"},{LogicalName=$logic3;Connector="or"}
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Existence**

This parameter is implied and optional.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Hive**

Specify the registry hive where the key exists. Use the KeyName parameter to specify the key name.



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

Specify the name of the registry key that must exist to indicate the presence of this application. Use the Hive parameter to specify the registry hive where this key should exist.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |RegistryKey|





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
New-CMDetectionClauseRegistryKey [-DisableWildcardHandling] [-Existence] [-ForceWildcardHandling] -Hive {ClassesRoot | CurrentConfig | CurrentUser | LocalMachine | Users} [-Is64Bit] -KeyName <String> [<CommonParameters>]
```
