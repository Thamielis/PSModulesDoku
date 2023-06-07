New-CMAppVVirtualEnvironment
----------------------------




### Synopsis
Creates an App-V virtual environment.



---


### Description

The New-CMAppVVirtualEnvironment cmdlet creates an Microsoft Application Virtualization (App-V) virtual environment in Configuration Manager. App-V virtual environments in Configuration Manager enable deployed virtual applications to share the same file system and registry on client computers.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAppVVirtualEnvironment](Get-CMAppVVirtualEnvironment)



* [New-CMVirtualEnvironmentGroup](New-CMVirtualEnvironmentGroup)



* [Remove-CMAppVVirtualEnvironment](Remove-CMAppVVirtualEnvironment)



* [Set-CMAppVVirtualEnvironment](Set-CMAppVVirtualEnvironment)





---


### Examples
#### Example 1: Create an App-V virtual environment
```PowerShell
PS XYZ:\> $Dti = Get-CMAppV5XDeploymentTypeItem -ApplicationName "App01d2012" -DeploymentTypeName "7Zip - Microsoft Application Virtualization 5"
PS XYZ:\> $Veg = New-CMVirtualEnvironmentGroup -Name "Venvgroup01" -DeploymentType $Dti
PS XYZ:\> New-CMAppVVirtualEnvironment -Name "CMAppVenv01" -Description "App-V virtual environment" -ApplicationGroup $Veg
```
This first command uses the Get-CMAppV5XDeploymentTypeItem cmdlet gets the deployment type named 7Zip - Microsoft Application Virtualization 5 in the application named App01d2012. The command stores the result in the $Dti variable.


This second command creates an application group named Venvgroup01 for the deployment type stored in $Dti. The command stores the result in the $Veg variable.


This third command creates an App-V virtual environment named CMAppVenv01 for the application group stored in $Veg.


---


### Parameters
#### **ApplicationGroup**

Specifies an array of application groups to add to the App-V virtual environment. To obtain an application group, use the New-CMVirtualEnvironmentGroup cmdlet.






|Type                         |Required|Position|PipelineInput|
|-----------------------------|--------|--------|-------------|
|`[VirtualEnvironmentGroup[]]`|true    |named   |False        |



#### **Description**

Specifies a description for the App-V virtual environment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **Name**

Specifies a name for the App-V virtual environment.






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
None





---


### Outputs
* IResultObject#SMS_VirtualEnvironment






---


### Notes




---


### Syntax
```PowerShell
New-CMAppVVirtualEnvironment -ApplicationGroup <VirtualEnvironmentGroup[]> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
