Remove-CMSoftwareUpdateAutoDeploymentRule
-----------------------------------------




### Synopsis
Removes Configuration Manager deployment rules for automatic software updates.



---


### Description

The Remove-CMSoftwareUpdateAutoDeploymentRule cmdlet removes specified Configuration Manager deployment rules for automatic software updates.



Configuration Manager uses rules to manage automatic deployment of software updates. When a rule runs, Configuration Manager adds updates that qualify for the rule to a software update group. The Configuration Manager server downloads content files and copies them to distribution points, and then updates client computers.



You can specify rules to remove by ID or by name, or specify a rule object by using the Get-CMSoftwareUpdateAutoDeploymentRule (Get-CMSoftwareUpdateAutoDeploymentRule.md)cmdlet. This cmdlet deletes rules permanently. You can use the Disable-CMSoftwareUpdateAutoDeploymentRule (Disable-CMSoftwareUpdateAutoDeploymentRule.md)cmdlet to suspend a rule.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMSoftwareUpdateAutoDeploymentRule](Disable-CMSoftwareUpdateAutoDeploymentRule)



* [Enable-CMSoftwareUpdateAutoDeploymentRule](Enable-CMSoftwareUpdateAutoDeploymentRule)



* [Get-CMSoftwareUpdateAutoDeploymentRule](Get-CMSoftwareUpdateAutoDeploymentRule)



* [Invoke-CMSoftwareUpdateAutoDeploymentRule](Invoke-CMSoftwareUpdateAutoDeploymentRule)





---


### Examples
#### Example 1: Remove a deployment rule by name
```PowerShell
PS XYZ:\> Remove-CMSoftwareUpdateAutoDeploymentRule -Name "Weekly Driver Updates"
Remove
Are you sure you wish to remove SoftwareUpdateAutoDeploymentRule: Name="Weekly Driver Updates"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```
This command removes a rule named Weekly Driver Updates. Because the command does not include the Force parameter, the cmdlet prompts you before it deletes the rule.
#### Example 2: Remove a deployment rule by ID
```PowerShell
PS XYZ:\> Remove-CMSoftwareUpdateAutoDeploymentRule -Id "16777217" -Force
```
This command disables a deployment rule that has the ID 16777217. This command includes the Force parameter, so the cmdlet does not prompt you before it removes the rule.
#### Example 3: Remove a deployment rule by using a variable
```PowerShell
PS XYZ:\> $CMSUADR = Get-CMSoftwareUpdateAutoDeploymentRule -Name "Weekly Driver Updates"
PS XYZ:\> Remove-CMSoftwareUpdateAutoDeploymentRule -InputObject $CMSUADR -Force
```
The first command gets a deployment rule that has the specified name, and then stores it in the $CMSUADR variable.


The second command removes the rule stored in the variable.


---


### Parameters
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



#### **Id**

Specifies an array of IDs for rules for automatic deployment of software updates. This value is the AutoDeploymentID property of the deployment rule object.






|Type     |Required|Position|PipelineInput|Aliases         |
|---------|--------|--------|-------------|----------------|
|`[Int32]`|true    |0       |False        |AutoDeploymentId|



#### **InputObject**

Specifies a software update automatic deployment rule object. To obtain a deployment rule object, use Get-CMSoftwareUpdateAutoDeploymentRule .






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies a name of a rule for automatic deployment of software updates.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



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
Remove-CMSoftwareUpdateAutoDeploymentRule [-Id] <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateAutoDeploymentRule [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateAutoDeploymentRule [-Name] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
