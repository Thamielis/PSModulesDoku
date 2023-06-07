Set-CMBaselineDeployment
------------------------




### Synopsis
Changes settings for a Configuration Manager baseline deployment.



---


### Description

The Set-CMBaselineDeployment cmdlet changes settings for a Configuration Manager baseline configuration deployment. A baseline defines the configuration of a product or system established at a specific time. Baselines contain a defined set of required configurations and associated rules. Configuration Manager assigns baselines to computer in collections, together with a compliance evaluation schedule.



Use the baseline and the name of a collection to specify a deployment to modify. You can specify a baseline by its name or ID, or use the Get-CMBaseline cmdlet to get a baseline object.



You can use the New-CMBaselineDeployment cmdlet to create a deployment.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMBaselineDeployment](New-CMBaselineDeployment)



* [Get-CMBaseline](Get-CMBaseline)





---


### Examples
#### Example 1: Change whether a deployment generates alerts
```PowerShell
PS XYZ:\> Set-CMBaselineDeployment -BaselineName "Baseline 2012" -CollectionName "All Computers" -GenerateAlert $False
```
This command changes a deployment for the baseline named Baseline 2012 for a collection named All Computers. This command sets the GenerateAlert parameter to $False.
#### Example 2: Change deployment settings
```PowerShell
PS XYZ:\> Set-CMBaselineDeployment -BaselineName "Baseline A3" -CollectionName "TSQA Computers" -GenerateAlert $True -MonitoredByScom $True -ParameterValue 60 -PostponeDate 2013/02/12 -PostponeTime 12:34
```
This command changes a deployment for the baseline named Baseline A3 for a collection named TSQA Computers. The command specifies values for generation of alerts and Operations Manager monitoring. It also includes as a parameter value and postpone date and time.


---


### Parameters
#### **BaselineId**

Specifies the ID of a baseline.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BaselineName**

Specifies the name of a baseline.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Collection**








|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specifies the name of a collection. The deployment applies to this collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableEnforcement**

Specifies whether to enable enforcement for the baseline. During enforcement, a client reports compliance information about the configurations in a baseline.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateAlert**

Specifies whether Configuration Manager generates alerts during the deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases                                      |
|-----------------|--------|--------|--------------|---------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Baseline<br/>DeploymentSummary<br/>Assignment|



#### **MonitoredByScom**

Specifies whether to apply System Center 2016 - Operations Manager monitoring criteria during the deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **OverrideServiceWindow**

Specifies whether to override service windows while deploying policies. Service windows are periods of time allocated for maintenance.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ParameterValue**

Specifies an integer value. This is the parameter value.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PostponeDateTime**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **Schedule**

Specifies a CMSchedule object. The schedule specifies when the maintenance window occurs. To create a CMSchedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






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
Set-CMBaselineDeployment -BaselineId <String> [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBaselineDeployment -BaselineName <String> [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBaselineDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] -InputObject <IResultObject> [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
