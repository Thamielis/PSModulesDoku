New-CMBaselineDeployment
------------------------




### Synopsis
Create a baseline deployment.



---


### Description

Deploy a configuration baseline. Use the Get-CMBaseline (Get-CMBaseline.md)cmdlet to get a baseline.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBaseline](Get-CMBaseline)



* [Get-CMCollection](Get-CMCollection)



* [New-CMSchedule](New-CMSchedule)





---


### Examples
#### Example 1: Deploy a baseline to collections with the same named prefix
```PowerShell
$BaselineName = Get-CMBaseline -Name 'ConfigMgr Baseline'
$DeployToCollections = Get-CMCollection -Name 'Collection_Name*' | Sort-Object -Property "Name"
$BaselineSchedule = New-CMSchedule -DurationInterval Days -DurationCount 0 -RecurInterval Days -RecurCount 1

foreach ($Collection in $DeployToCollection)
             {
             New-CMBaselineDeployment -InputObject $BaselineName -CollectionID $Collection.CollectionId -Schedule $BaselineSchedule
             Write-Output "Created Deployment for $($BaselineName.LocalizedDisplayName) on $($Collection.Name)"
             }
```

#### Example 2: Deploy a baseline to one collection
```PowerShell
$BaselineSchedule = New-CMSchedule -DurationInterval Days -DurationCount 0 -RecurInterval Days -RecurCount 1
New-CMBaselineDeployment -Name "MY_Baseline" -CollectionID "PS1000023" -Schedule $BaselineSchedule
```



---


### Parameters
#### **Collection**

Specify a collection object as the target of the baseline deployment.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify the ID of the collection as the target of the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the name of the collection as the target of the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableEnforcement**

If `$true`, remediate noncompliant rules when supported.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateAlert**

If `$true`, generate an alert.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Id**

Specify the ID of the configuration baseline to deploy.






|Type     |Required|Position|PipelineInput|Aliases                      |
|---------|--------|--------|-------------|-----------------------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID<br/>BaselineId|



#### **InputObject**

Specify a configuration baseline object to deploy. Use the Get-CMBaseline (Get-CMBaseline.md)cmdlet to get a baseline.






|Type             |Required|Position|PipelineInput |Aliases |
|-----------------|--------|--------|--------------|--------|
|`[IResultObject]`|true    |0       |True (ByValue)|Baseline|



#### **MonitoredByScom**

If `$true`, generate a System Center Operations Manager alert.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify the name of the configuration baseline to deploy.






|Type      |Required|Position|PipelineInput|Aliases                              |
|----------|--------|--------|-------------|-------------------------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName<br/>BaselineName|



#### **OverrideServiceWindow**

If `$true`, allow the client to remediate this baseline outside of maintenance windows.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ParameterValue**

If you use the -GenerateAlert parameter, specify an integer value as a percentage (0-100). When compliance of this configuration baseline is below this value, the site generates an alert.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PostponeDateTime**

This parameter corresponds to the Date and time property of the configuration baseline when you use the -GenerateAlert parameter.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **Schedule**

Specify a schedule object for when the client evaluates this configuration baseline. Use the New-CMSchedule (New-CMSchedule.md)cmdlet to create a schedule.






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
New-CMBaselineDeployment [-Id] <Int32> [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMBaselineDeployment [-InputObject] <IResultObject> [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMBaselineDeployment [-Name] <String> [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
