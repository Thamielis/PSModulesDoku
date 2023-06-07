Set-CMSoftwareMeteringSetting
-----------------------------




### Synopsis
Configures Configuration Manager software metering properties.



---


### Description

The Set-CMSoftwareMeteringSetting cmdlet configures software metering properties for Configuration Manager.



Software metering can use software inventory information to create software metering rules. When you select this feature, Configuration Manager identifies multiple computers that use the same software and creates a rule to track that usage. You decide how long to keep software metering data that Configuration Manager uses to create rules.



To prevent Configuration Manager from creating too many rules, you can specify what percentage of computers use a piece of software before Configuration Manager creates a rule.



You can also set a rule threshold. If the number of software metering rules exceeds this threshold, Configuration Manager stops automatically creating rules.



When Configuration Manager creates a rule automatically, it creates that rule as disabled. A disabled rule does not collect information from clients. You can use the Enable-CMSoftwareMeteringRule (Enable-CMSoftwareMeteringRule.md)cmdlet to enable a rule. You can use the Remove-CMSoftwareMeteringRule (Remove-CMSoftwareMeteringRule.md)cmdlet to remove unwanted rules.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMSoftwareMeteringRule](Enable-CMSoftwareMeteringRule)



* [Get-CMSoftwareMeteringSetting](Get-CMSoftwareMeteringSetting)



* [Remove-CMSoftwareMeteringRule](Remove-CMSoftwareMeteringRule)





---


### Examples
#### Example 1: Disable automatic rule creation
```PowerShell
PS XYZ:\> Set-CMSoftwareMeteringSetting -AutoCreateDisabledRule $False
```
This command disables automatic rule creation. Configuration Manager does not automatically create software metering rules after you run this command.
#### Example 2: Configure automatic rule creation
```PowerShell
PS XYZ:\> Set-CMSoftwareMeteringSetting -AutoCreateDisabledRule $True -AutoCreatePercentage 50 -AutoCreateThreshold 200 -DataRetentionDayCount 30
```
This command enables automatic rule creation and sets properties for it. This command sets the percentage of computers that use a piece of software to 50 percent, the rule threshold to 200, and the amount of time Configuration Manager keeps software metering data to 30 days.
#### Example 3: Change automatic rule creation percentage
```PowerShell
PS XYZ:\> Set-CMSoftwareMeteringSetting -AutoCreatePercentage 20
```
This command changes the percentage of computers that use a piece of software to 20 percent.


---


### Parameters
#### **AutoCreateDisabledRule**

Specifies whether Configuration Manager automatically creates software metering rules. If this value is $True, Configuration Manager automatically creates software metering rules. If this value is $False, it does not automatically create rules.


When Configuration Manager creates rules, it creates them as disabled.


You can use the values set by other parameters of this cmdlet to limit creation of rules.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AutoCreatePercentage**

Specifies a percentage of computers that use a piece of software for Configuration Manager to create a rule. Software metering calculates the number of computers as all the computers monitored for software metering by Configuration Manager, not just for a single site. Valid values are integers from 1 through 99.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **AutoCreateThreshold**

Specifies a number of software metering rules as a threshold. When Configuration Manager exceeds this threshold, it stops automatically creating rules. The number of rules counted for this threshold includes all software metering rules, not only those that Configuration Manager creates automatically. Valid values are integers from 1 through 1000.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DataRetentionDayCount**

Specifies the number of days that Configuration Manager keeps software metering data.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMSoftwareMeteringSetting [-AutoCreateDisabledRule <Boolean>] [-AutoCreatePercentage <Int32>] [-AutoCreateThreshold <Int32>] [-DataRetentionDayCount <Int32>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
