Remove-CMUser
-------------




### Synopsis
Removes a user from Configuration Manager.



---


### Description

The Remove-CMUser cmdlet removes user accounts from Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMUser](Get-CMUser)





---


### Examples
#### Example 1: Remove a user
```PowerShell
PS XYZ:\> $User = Get-CMUser -CollectionName "All Users" -Name "Contoso\user01"
PS XYZ:\> Remove-CMUser -InputObject $User -Force
```
The first command gets the user object named user01 from the All Users collection and stores the object in the $User variable.


The second command removes the user account stored in $User. Specifying the Force parameter indicates that the user is not prompted before the user account is removed.
#### Example 2: Remove a user by using the pipeline
```PowerShell
PS XYZ:\> Get-CMUser -CollectionName "All Users" -Name "Contoso\user02" | Remove-CMUser -Force
```
This command gets the user object named user02 from the All Users collection and uses the pipeline operator to pass the object to Remove-CMUser , which removes the user account. Specifying the Force parameter indicates that the user is not prompted before the user account is removed.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a Configuration Manager user account object. To obtain a Configuration Manager user account object, use the Get-CMUser (Get-CMUser.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies the name of a user account.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |0       |False        |UserName|



#### **ResourceId**

Specifies the resource ID of a user account.






|Type     |Required|Position|PipelineInput|Aliases      |
|---------|--------|--------|-------------|-------------|
|`[Int32]`|true    |0       |False        |Id<br/>UserId|



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
Remove-CMUser [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUser [-Name] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUser [-ResourceId] <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
