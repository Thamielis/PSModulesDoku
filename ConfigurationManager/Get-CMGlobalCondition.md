Get-CMGlobalCondition
---------------------




### Synopsis
Gets Configuration Manager global condition objects.



---


### Description

The Get-CMGlobalCondition cmdlet gets global condition objects. You can pass the results of this cmdlet to the Set-CMGlobalCondition cmdlet or the Remove-CMGlobalCondition cmdlet.



Configuration Manager uses global conditions to represent business or technical conditions. Global conditions specify how to provide and deploy applications to client devices.



You can get global conditions by name, ID, or security scope. You can also specify one or more security scope names with either names or IDs. For instance, you might specify an array of global condition names and specify a security scope to narrow your results.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMGlobalCondition](New-CMGlobalCondition)



* [Set-CMGlobalCondition](Set-CMGlobalCondition)



* [Remove-CMGlobalCondition](Remove-CMGlobalCondition)





---


### Examples
#### Example 1: Get a global condition by name
```PowerShell
PS XYZ:\> Get-CMGlobalCondition -Name "CPU speed"
```
This command gets the global condition named CPU speed.
#### Example 2: Get a global condition by id (CI_ID)
```PowerShell
PS XYZ:\> $test = Get-CMGlobalCondition -Id 16777504
        $test.CI_ID
```



---


### Parameters
#### **AsDcmSdkObject**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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



#### **Id**

Specifies an array of identifiers of global conditions. This value corresponds to the CI_ID property of a global condition object.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |CIId   |



#### **Name**

Specifies an array of names for global conditions. This value corresponds to the LocalizedDisplayName property of a global condition object.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDisplayName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_GlobalCondition


* IResultObject#SMS_GlobalCondition


* ConfigurationItem






---


### Notes




---


### Syntax
```PowerShell
Get-CMGlobalCondition [-AsDcmSdkObject] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMGlobalCondition [-AsDcmSdkObject] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
