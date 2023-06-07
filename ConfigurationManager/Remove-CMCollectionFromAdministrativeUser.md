Remove-CMCollectionFromAdministrativeUser
-----------------------------------------




### Synopsis
Removes a collection from administrative user.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



---


### Parameters
#### **CollectionId**








|Type      |Required|Position|PipelineInput|Aliases                                |
|----------|--------|--------|-------------|---------------------------------------|
|`[String]`|true    |named   |False        |DeviceCollectionId<br/>UserCollectionId|



#### **CollectionName**








|Type      |Required|Position|PipelineInput|Aliases                                    |
|----------|--------|--------|-------------|-------------------------------------------|
|`[String]`|true    |named   |False        |DeviceCollectionName<br/>UserCollectionName|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases                                           |
|-----------------|--------|--------|--------------|--------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeviceCollection<br/>UserCollection<br/>Collection|



#### **User**








|Type             |Required|Position|PipelineInput |Aliases           |
|-----------------|--------|--------|--------------|------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|AdministrativeUser|



#### **UserId**








|Type     |Required|Position|PipelineInput|Aliases             |
|---------|--------|--------|-------------|--------------------|
|`[Int32]`|true    |named   |False        |AdministrativeUserId|



#### **UserName**








|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|true    |named   |False        |AdministrativeUserName|



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
Remove-CMCollectionFromAdministrativeUser -CollectionId <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -UserId <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionFromAdministrativeUser -CollectionId <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -UserName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionFromAdministrativeUser -CollectionId <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -User <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionFromAdministrativeUser -CollectionName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -UserName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionFromAdministrativeUser -CollectionName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -UserId <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionFromAdministrativeUser -CollectionName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -User <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionFromAdministrativeUser [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> -UserId <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionFromAdministrativeUser [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> -UserName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionFromAdministrativeUser [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> -User <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
