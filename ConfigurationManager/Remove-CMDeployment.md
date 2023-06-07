Remove-CMDeployment
-------------------




### Synopsis
Removes a deployment.



---


### Description

The Remove-CMDeployment cmdlet removes an application deployment from Configuration Manager.



When you remove an application deployment, Configuration Manager does not remove instances of the application that it has already installed. To remove these applications, you must deploy the application to computers with the action Uninstall. If you delete an application deployment, or remove a resource from the collection you are deploying to, the application will no longer be visible in Software Center.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeployment](Get-CMDeployment)



* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Remove-CMDeploymentType](Remove-CMDeploymentType)





---


### Examples
#### Example 1: Remove an application deployment
```PowerShell
PS XYZ:\> Remove-CMDeployment -ApplicationName "CMappD01" -CollectionName "All Users"
```
This command removes the Configuration Manager deployment that is associated with the application named CMappD01 and that is applied to the collection named All Users.
#### Example 2: Pass a deployment object and remove it
```PowerShell
PS XYZ:\> Get-CMDeployment -CollectionName "deviceCol01" -FeatureType Application | Remove-CMDeployment -Force
```
This command gets the specified application deployment object for the collection named deiceCol01 and uses the pipeline operator to pass the object to Remove-CMDeployment , which removes the deployment. Because the Force parameter is specified, the user is not prompted before the deployment is removed.
#### Example 3: Remove a deployment by its ID
```PowerShell
PS XYZ:\> Remove-CMDeployment -DeploymentId "{890082B6-7C16-4600-8807-7E0003BC9D99}" -ApplicationName "application01" -Force
```
This command removes the deployment named application01 with the specified ID. Because the Force parameter is specified, the user is not prompted before the deployment is removed.


---


### Parameters
#### **ApplicationName**

Specifies the name of the application associated with the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specifies the name of the collection associated with the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeploymentId**

Specifies the ID of a deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Performs the action without a confirmation message.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a deployment object. To obtain a deployment object, use the Get-CMDeployment cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Deployment|



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
Remove-CMDeployment -ApplicationName <String> -DeploymentId <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeployment -ApplicationName <String> -CollectionName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
