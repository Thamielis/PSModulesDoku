Remove-CMDeploymentType
-----------------------




### Synopsis
Removes a deployment type for a Configuration Manager deployment application.



---


### Description

The Remove-CMDeploymentType cmdlet removes a deployment type in Configuration Manager. You cannot remove a deployment type if it is referenced by a deployment type in another application.



To remove a deployment type, you must remove any dependencies to the deployment type in other deployment types. Additionally, you must remove previous revisions of any application that contains a deployment type that references the deployment type that you want to remove. If you have already deployed the application, you cannot remove the last deployment type that the application contains, and the application must be in an active state.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeployment](Get-CMDeployment)



* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Set-CMDeploymentType](Set-CMDeploymentType)





---


### Examples
#### Example 1: Remove a deployment type
```PowerShell
PS XYZ:\> Remove-CMDeploymentType -ApplicationName "CenterApp" -DeploymentTypeName "InterDept - Windows app package (.appx file)"
```
This command removes the deployment type named InterDept - Windows app package (.appx file) that is contained in the application named CenterApp.


---


### Parameters
#### **ApplicationName**

Specifies the name of an application that is associated to the deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentTypeId**

Specifies the ID of a deployment type.






|Type     |Required|Position|PipelineInput|Aliases              |
|---------|--------|--------|-------------|---------------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID<br/>Id|



#### **DeploymentTypeName**

Specifies the name of a deployment type.






|Type      |Required|Position|PipelineInput|Aliases                      |
|----------|--------|--------|-------------|-----------------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName<br/>Name|



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

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



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
Remove-CMDeploymentType [-ApplicationName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeploymentType -ApplicationName <String> -DeploymentTypeId <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeploymentType [-DeploymentTypeName] <String> -ApplicationName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
