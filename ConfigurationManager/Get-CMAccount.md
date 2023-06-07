Get-CMAccount
-------------




### Synopsis
Gets a named user account.



---


### Description

The Get-CMAccount cmdlet gets a Configuration Manager user account. The user name must be in the domain\user format. For more information about Configuration Manager user accounts, see Technical Reference for Accounts Used in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/accounts).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAccount](New-CMAccount)



* [Remove-CMAccount](Remove-CMAccount)



* [Set-CMAccount](Set-CMAccount)





---


### Examples
#### Example 1: Get a user account by using its name
```PowerShell
PS XYZ:\> Get-CMAccount -Name "CONTOSO\ENarvaez"
```
This command gets a user account.


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



#### **SiteCode**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserName**








|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |0       |False        |Name   |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_Reserved


* IResultObject#SMS_SCI_Reserved






---


### Notes




---


### Syntax
```PowerShell
Get-CMAccount [[-UserName] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
