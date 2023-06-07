Set-CMAccount
-------------




### Synopsis
Sets a Configuration Manager user account.



---


### Description

The Set-CMAccount cmdlet sets a user account in Configuration Manager. A CMAccount is a user account that Configuration Manager uses to connect to various system and network resources. For more information about user accounts, see Technical Reference for Accounts Used in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/accounts).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAccount](Get-CMAccount)



* [New-CMAccount](New-CMAccount)



* [Remove-CMAccount](Remove-CMAccount)





---


### Examples
#### Example 1: Set an account by using name and password
```PowerShell
PS XYZ:\> $Secure = ConvertTo-SecureString -String "Pas$W0rd02" -AsPlainText -Force
PS XYZ:\> Set-CMAccount -Name "TSQA\PFuller" -Password $Secure -SiteCode "CM2"
```
The first command creates a variable as a secure string.


The second command sets the password for the account.


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

Specifies a user account object. You can get a user account object by using the Get-CMAccount cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Account|



#### **Password**

Specifies a secure string that contains the password for the user account.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **SiteCode**

Specifies a Configuration Manager site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserName**








|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


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
Set-CMAccount [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Password <SecureString>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAccount [-DisableWildcardHandling] [-ForceWildcardHandling] [-Password <SecureString>] [-SiteCode <String>] -UserName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
