Start-CMBaselineDeployment
--------------------------




### Synopsis
(Deprecated) Starts deployment of a Configuration Manager baseline configuration to a collection of computers.



---


### Description

> [!IMPORTANT] > This cmdlet is deprecated. Use New-CMBaselineDeployment (New-CMBaselineDeployment.md)instead.



The Start-CMBaselineDeployment cmdlet starts the deployment of a Configuration Manager baseline configuration to a collection of computers.



A baseline defines the configuration of a product or system established at a specific time. Baselines contain a defined set of required configurations and associated rules. Configuration Manager assigns baselines to computer in collections, together with a compliance evaluation schedule.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMBaselineDeployment](Set-CMBaselineDeployment)





---


### Examples
#### Example 1: Start baseline deployment
```PowerShell
PS XYZ:\> Start-CMBaselineDeployment -CollectionName "All Users" -Name "Baseline22" -EnableEnforcement $True -GenerateAlert $True -MonitoredByScom $True -OverrideServiceWindow $True -ParameterValue 30
```
This command starts a baseline deployment named Baseline22 for the collection All Users. The command enables enforcement, generates alerts, monitors the deployment using Operations Manager, and overrides defined service windows. The command specifies a parameter value of 30.


---


### Parameters
#### **CollectionName**

Specifies a name of a collection. The deployment applies to this collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableEnforcement**

Indicates whether to enable enforcement for the deployment. During enforcement, a client reports compliance information about a deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateAlert**

Indicates whether Configuration Manager generates alerts during the deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Id**

Specifies an array of IDs of baseline deployments.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a baseline deployment object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **MonitoredByScom**

Specifies whether to apply System Center 2016 - Operations Manager monitoring criteria during the deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specifies an array of names for baseline deployments.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **OverrideServiceWindow**

Indicates whether to override service windows while deploying policies. Service windows are periods of time allocated for maintenance.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ParameterValue**

Specifies an integer value. This is the parameter value.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PostponeDate**

Specifies a date, as a DateTime object. To obtain a DateTime object, use the Get-Date cmdlet. For more information, type `Get-Help Get-Date`. This is the date for the deployment if postponed.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **PostponeTime**

Specifies a time, as a DateTime object. To obtain a DateTime object, use the Get-Date cmdlet. This is the time for the deployment if postponed.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **Schedule**

Specifies a CMSchedule object. To create a CMSchedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



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
Start-CMBaselineDeployment [-Id] <Int32> -CollectionName <String> [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PostponeDate <DateTime>] [-PostponeTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMBaselineDeployment [-InputObject] <IResultObject> -CollectionName <String> [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PostponeDate <DateTime>] [-PostponeTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMBaselineDeployment [-Name] <String> -CollectionName <String> [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PostponeDate <DateTime>] [-PostponeTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
