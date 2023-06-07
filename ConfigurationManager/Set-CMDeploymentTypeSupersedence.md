Set-CMDeploymentTypeSupersedence
--------------------------------




### Synopsis
Configure a supersedence relationship on an application. This cmdlet is deprecated.



---


### Description

> [!IMPORTANT] > Starting in version 2111, this cmdlet is deprecated and may be removed in a future release. Use the Set-CMApplicationSupersedence (Set-CMApplicationSupersedence.md)cmdlet instead.



Use this cmdlet to configure a supersedence relationship on an application.



For more information, see Supersede applications in Configuration Manager (/mem/configmgr/apps/deploy-use/revise-and-supersede-applications#supersedence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMApplicationSupersedence](Set-CMApplicationSupersedence)



* [Get-CMDeploymentTypeSupersedence](Get-CMDeploymentTypeSupersedence)



* [Supersede applications in Configuration Manager](Supersede applications in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
$dt7 = Get-CMDeploymentType -ApplicationName "LOB app v7" -DeploymentTypeName "Install"
$dt6 = Get-CMDeploymentType -ApplicationName "LOB app v6" -DeploymentTypeName "Install"

Set-CMDeploymentTypeSupersedence -SupersedingDeploymentType $dt7 -InputObject $dt6 -IsUninstall $true
```



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

Specify a deployment type object for the application to supersede. In other words, the old deployment type. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md) or [Get-CMDeploymentTypeSupersedence](Get-CMDeploymentTypeSupersedence.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases                 |
|-----------------|--------|--------|--------------|------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SupersededDeploymentType|



#### **IsUninstall**

If `$false`, the new deployment type (superseding) will upgrade the installed deployment type (superseded). If you set this parameter to `$true`, Configuration Manager uninstalls the previous deployment type when it installs the new deployment type.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SupersedingDeploymentType**

Specify a deployment type object for the application to supersede the other. In other words, the replacement deployment type. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



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
Set-CMDeploymentTypeSupersedence [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsUninstall <Boolean>] [-PassThru] -SupersedingDeploymentType <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
