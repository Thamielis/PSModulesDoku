Remove-CMApplicationPhasedDeployment
------------------------------------




### Synopsis
Use this cmdlet to remove a phased deployment for an application.



---


### Description

Use this cmdlet to remove a phased deployment for an application.



---


### Examples
#### Example 1: Remove a phased deployment on an application
```PowerShell
Remove-CMApplicationPhasedDeployment -ApplicationName "myApplicationName"
```

#### Example 2: Remove a phased deployment by name
```PowerShell
Remove-CMApplicationPhasedDeployment -Name "myPhasedDeploymentName"
```

#### Example 3: Force remove a phased deployment from input
```PowerShell
$myPhasedDeployment | Remove-CMApplicationPhasedDeployment -Force
```



---


### Parameters
#### **Application**

Specify an application object that has the phased deployment to remove.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **ApplicationId**

Specify the ID of the application with the phased deployment to remove.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |CIId<br/>CI_ID|



#### **ApplicationName**

Specify the name of the application with the phased deployment to remove.






|Type      |Required|Position|PipelineInput|Aliases                        |
|----------|--------|--------|-------------|-------------------------------|
|`[String]`|true    |named   |False        |ApplicationLocalizedDisplayName|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Force remove the phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the phased deployment to remove. This ID is a GUID format.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |PhasedDeploymentId|



#### **InputObject**

Specify a phased deployment object to remove.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|PhasedDeployment|



#### **Name**

Specify the name of the phased deployment to remove.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMApplicationPhasedDeployment -Application <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationPhasedDeployment -ApplicationId <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationPhasedDeployment -ApplicationName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationPhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationPhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationPhasedDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
