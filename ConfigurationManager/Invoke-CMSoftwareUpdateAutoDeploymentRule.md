Invoke-CMSoftwareUpdateAutoDeploymentRule
-----------------------------------------




### Synopsis
Runs a Configuration Manager deployment rule for automatic software updates.



---


### Description

The Invoke-CMSoftwareUpdateAutoDeploymentRule cmdlet runs a Configuration Manager deployment rule for automatic software updates immediately instead of according to its schedule.



Configuration Manager uses rules to manage automatic deployment of software updates. When a rule runs, Configuration Manager adds updates that qualify for the rule to a software update group. The Configuration Manager server downloads content files and copies them to distribution points, and then updates client computers.



You can specify rules to run by ID or by name, or specify a rule object by using the Get-CMSoftwareUpdateAutoDeploymentRule (Get-CMSoftwareUpdateAutoDeploymentRule.md)cmdlet. You cannot run a disabled rule. You can use the Enable-CMSoftwareUpdateAutoDeploymentRule (Enable-CMSoftwareUpdateAutoDeploymentRule.md)cmdlet to enable a rule and then run it.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMSoftwareUpdateAutoDeploymentRule](Disable-CMSoftwareUpdateAutoDeploymentRule)



* [Enable-CMSoftwareUpdateAutoDeploymentRule](Enable-CMSoftwareUpdateAutoDeploymentRule)



* [Get-CMSoftwareUpdateAutoDeploymentRule](Get-CMSoftwareUpdateAutoDeploymentRule)



* [Remove-CMSoftwareUpdateAutoDeploymentRule](Remove-CMSoftwareUpdateAutoDeploymentRule)





---


### Examples
#### Example 1: Invoke a deployment rule
```PowerShell
PS XYZ:\>Invoke-CMSoftwareUpdateAutoDeploymentRule -Name "Weekly Security Updates"
```
This command runs a rule called Weekly Security Updates.


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

Specifies an array of IDs for rules for automatic deployment of software updates. This value is the AutoDeploymentID property of the deployment rule object.






|Type       |Required|Position|PipelineInput|Aliases         |
|-----------|--------|--------|-------------|----------------|
|`[Int32[]]`|true    |named   |False        |AutoDeploymentId|



#### **InputObject**

Specifies a software update automatic deployment rule object. To obtain a deployment rule object, use the Get-CMSoftwareUpdateAutoDeploymentRule cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name of a rule for automatic deployment of software updates.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Invoke-CMSoftwareUpdateAutoDeploymentRule [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32[]> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMSoftwareUpdateAutoDeploymentRule [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMSoftwareUpdateAutoDeploymentRule [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
