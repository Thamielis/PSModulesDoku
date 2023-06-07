Get-CMAppVVirtualEnvironment
----------------------------




### Synopsis
Gets an App-V virtual environment.



---


### Description

The Get-CMAppVVirtualEnvironment cmdlet gets one or more Microsoft Application Virtualization (App-V) virtual environment objects from Configuration Manager. You can specify App-V environments by name or ID.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAppVVirtualEnvironment](New-CMAppVVirtualEnvironment)



* [Remove-CMAppVVirtualEnvironment](Remove-CMAppVVirtualEnvironment)



* [Set-CMAppVVirtualEnvironment](Set-CMAppVVirtualEnvironment)





---


### Examples
#### Example 1: Get all virtual environments
```PowerShell
PS XYZ:\> Get-CMAppVVirtualEnvironment
```
This command gets all App-V virtual environments.
#### Example 2: Get virtual environments by using a wildcard
```PowerShell
PS XYZ:\> Get-CMAppVVirtualEnvironment -Name "T*"
```
This command gets all App-V virtual environments that have names that begin with the letter T.
#### Example 3: Get virtual environment by an ID
```PowerShell
PS XYZ:\> Get-CMAppVVirtualEnvironment -Id "16781806"
```
This command gets an App-V virtual environment that has the ID 16781806.


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



#### **Id**

Specifies an array of IDs of virtual environments.






|Type       |Required|Position|PipelineInput|Aliases       |
|-----------|--------|--------|-------------|--------------|
|`[Int32[]]`|true    |named   |False        |CIId<br/>CI_ID|



#### **Name**

Specifies an array of names of App-V virtual environment objects. You can use a wildcard.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDisplayName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_VirtualEnvironment


* IResultObject#SMS_VirtualEnvironment






---


### Notes




---


### Syntax
```PowerShell
Get-CMAppVVirtualEnvironment [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32[]> [<CommonParameters>]
```
```PowerShell
Get-CMAppVVirtualEnvironment [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
