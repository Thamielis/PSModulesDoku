Disable-CMSoftwareUpdateAutoDeploymentRule
------------------------------------------




### Synopsis
Disables Configuration Manager deployment rules for automatic software updates.



---


### Description

The Disable-CMSoftwareUpdateAutoDeploymentRule cmdlet disables specified Configuration Manager deployment rules for automatic software updates. While a rule is disabled, it does not run in accordance with its schedule and you cannot run it manually.



Configuration Manager uses rules to manage automatic deployment of software updates. When a rule runs, Configuration Manager adds updates that qualify for the rule to a software update group. The Configuration Manager server downloads content files and copies them to distribution points, and then updates client computers.



You can specify rules to disable by ID or by name, or specify a rule object by using the Get-CMSoftwareUpdateAutoDeploymentRule (Get-CMSoftwareUpdateAutoDeploymentRule.md)cmdlet. You can use the Enable-CMSoftwareUpdateAutoDeploymentRule (Enable-CMSoftwareUpdateAutoDeploymentRule.md)cmdlet to enable a rule. To remove a rule permanently, use the Remove-CMSoftwareUpdateAutoDeploymentRule (Remove-CMSoftwareUpdateAutoDeploymentRule.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMSoftwareUpdateAutoDeploymentRule](Enable-CMSoftwareUpdateAutoDeploymentRule)



* [Get-CMSoftwareUpdateAutoDeploymentRule](Get-CMSoftwareUpdateAutoDeploymentRule)



* [Invoke-CMSoftwareUpdateAutoDeploymentRule](Invoke-CMSoftwareUpdateAutoDeploymentRule)



* [New-CMSoftwareUpdateAutoDeploymentRule](New-CMSoftwareUpdateAutoDeploymentRule)



* [Remove-CMSoftwareUpdateAutoDeploymentRule](Remove-CMSoftwareUpdateAutoDeploymentRule)



* [Set-CMSoftwareUpdateAutoDeploymentRule](Set-CMSoftwareUpdateAutoDeploymentRule)





---


### Examples
#### Example 1: Disable a deployment rule by name
```PowerShell
PS XYZ:\>Disable-CMSoftwareUpdateAutoDeploymentRule -Name "Weekly Driver Updates"
```
This command disables a rule named Weekly Driver Updates.
#### Example 2: Disable a deployment rule by ID
```PowerShell
PS XYZ:\>Disable-CMSoftwareUpdateAutoDeploymentRule -Id "16777217"
```
This command disables a deployment rule that has the ID 16777217.
#### Example 3: Disable a deployment rule by using a variable
```PowerShell
PS XYZ:\> $CMSUADR = Get-CMSoftwareUpdateAutoDeploymentRule -Name "Weekly Driver Updates"
PS XYZ:\> Disable-CMSoftwareUpdateAutoDeploymentRule -InputObject $CMSUADR
```
The first command gets a deployment rule that has the specified name, and then stores it in the $CMSUADR variable.


The second command disables the rule stored in the variable.


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






|Type        |Required|Position|PipelineInput|Aliases         |
|------------|--------|--------|-------------|----------------|
|`[String[]]`|true    |named   |False        |AutoDeploymentId|



#### **InputObject**

Specifies a software update automatic deployment rule object. To obtain a deployment rule object, use Get-CMSoftwareUpdateAutoDeploymentRule .






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name of a rule for automatic deployment of software updates.






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
Disable-CMSoftwareUpdateAutoDeploymentRule [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Disable-CMSoftwareUpdateAutoDeploymentRule [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Disable-CMSoftwareUpdateAutoDeploymentRule [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
