New-CMSoftwareUpdateDeploymentPackage
-------------------------------------




### Synopsis
Create a software update deployment package.



---


### Description

Use this cmdlet to create a software update deployment package. A software update deployment package object contains one or more software updates. For more information, see Plan software update content (/mem/configmgr/sum/plan-design/plan-for-software-updates#bkmk_content).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateDeploymentPackage](Get-CMSoftwareUpdateDeploymentPackage)



* [Remove-CMSoftwareUpdateDeploymentPackage](Remove-CMSoftwareUpdateDeploymentPackage)



* [Set-CMSoftwareUpdateDeploymentPackage](Set-CMSoftwareUpdateDeploymentPackage)



* [Save-CMSoftwareUpdate](Save-CMSoftwareUpdate)





---


### Examples
#### Example 1: Create a deployment package
```PowerShell
$date = Get-Date -Format "yyyy-MM-dd"

New-CMSoftwareUpdateDeploymentPackage -Name "Updates for $date" -Path "\\gold\sources\updates\$date"
```



---


### Parameters
#### **Description**

Specify an optional description for the deployment package to help identify it.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specify the name for the deployment package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Path**

Specify the path of a network share to use as the package source for this software update deployment package.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|true    |named   |False        |PackageSourcePath|



#### **Priority**

Specify the distribution priority for this deployment package. The site uses this priority to determine the order in which packages are sent to other sites and the distribution points in the same site.



Valid Values:

* High
* Normal
* Low






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[Priorities]`|false   |named   |False        |



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
* IResultObject#SMS_SoftwareUpdatesPackage






---


### Notes
For more information on this return object and its properties, see SMS_SoftwareUpdatesPackage server WMI class (/mem/configmgr/develop/reference/sum/sms_softwareupdatespackage-server-wmi-class).



---


### Syntax
```PowerShell
New-CMSoftwareUpdateDeploymentPackage [-Description <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -Name <String> -Path <String> [-Priority {High | Normal | Low}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
