Restore-CMApplicationRevisionHistory
------------------------------------




### Synopsis
Restores a previous version of a Configuration Manager application from the application revision history.



---


### Description

The Restore-CMApplicationRevisionHistory cmdlet restores a previous version of a Configuration Manager application. You can use the revision history that Configuration Manager creates and maintains for each application to choose the version of the application that you want to restore.



If you restore an application version from the history, Configuration Manager might automatically replace currently installed copies of the application the next time it evaluates the deployment schedule. For more control over application replacement, create a new application that supersedes the application that you want to replace, and then deploy this application to the required collection.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplicationRevisionHistory](Get-CMApplicationRevisionHistory)



* [Remove-CMApplicationRevisionHistory](Remove-CMApplicationRevisionHistory)





---


### Examples
#### Example 1: Restore an application
```PowerShell
PS XYZ:\> Restore-CMApplicationRevisionHistory -Name "MSXML 6.0 Parser" -Revision 6.05
```
This command restores the application MSXML 6.0 Parser, version 6.05.


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

Specifies an array of IDs of application revision histories.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[UInt32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies an object that contains an application revision history. To get this object, use the Get-CMApplicationRevisionHistory cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |0       |True (ByValue)|Application|



#### **Name**

Specifies an array of names of application revision histories.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Revision**

Specifies the version number of the application revision that you restore.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|true    |1       |False        |



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
Restore-CMApplicationRevisionHistory [-Id] <UInt32> [-Revision] <UInt32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Restore-CMApplicationRevisionHistory [-InputObject] <IResultObject> [-Revision] <UInt32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Restore-CMApplicationRevisionHistory [-Name] <String> [-Revision] <UInt32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
