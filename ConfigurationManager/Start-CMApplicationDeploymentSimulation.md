Start-CMApplicationDeploymentSimulation
---------------------------------------




### Synopsis
(Deprecated) Starts an application deployment simulation in Configuration Manager.



---


### Description

The Start-CMApplicationDeploymentSimulation cmdlet starts an application deployment. Use simulated deployment to test an application deployment without installing an application.



> [!IMPORTANT] > Starting in version 2107, this cmdlet is deprecated and may be removed in a future release. Instead use the New-CMApplicationDeployment (New-CMApplicationDeployment.md)cmdlet with the Simulation parameter.



---


### Related Links
* [Set-CMApplicationDeployment](Set-CMApplicationDeployment)



* [Start-CMApplicationDeployment](Start-CMApplicationDeployment)





---


### Examples
#### Example 1: Start an application deployment simulation
```PowerShell
PS XYZ:\> Start-CMApplicationDeploymentSimulation -CollectionName "All Mobile Devices" -Name "WIN8_UPDATE2" -DeployAction Install
```
This command starts a deployment simulation of the installation of the application named WIN8_UPDATE2 for the target collection named All Mobile Devices.


---


### Parameters
#### **CollectionName**

Specifies a name for the target collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeploymentAction**





Valid Values:

* Install
* Uninstall






|Type                |Required|Position|PipelineInput|Aliases     |
|--------------------|--------|--------|-------------|------------|
|`[DeployActionType]`|false   |named   |False        |DeployAction|



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

Specifies an array of IDs.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies an application deployment object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies an array of names.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **PreDeploy**

Indicates whether to copy software to a device before installation.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
Start-CMApplicationDeploymentSimulation -CollectionName <String> [-DeploymentAction {Install | Uninstall}] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-PreDeploy <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMApplicationDeploymentSimulation -CollectionName <String> [-DeploymentAction {Install | Uninstall}] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PreDeploy <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMApplicationDeploymentSimulation -CollectionName <String> [-DeploymentAction {Install | Uninstall}] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PreDeploy <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
