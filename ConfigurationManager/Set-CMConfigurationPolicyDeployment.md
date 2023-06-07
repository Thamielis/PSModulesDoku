Set-CMConfigurationPolicyDeployment
-----------------------------------




### Synopsis
Creates a configuration policy deployment.



---


### Description

The Set-CMConfigurationPolicyDeployment cmdlet creates a configuration policy deployment in Configuration Manager. You can deploy firewall policies or user session management policies. Use the New-CMConfigurationPolicyDeployment (New-CMConfigurationPolicyDeployment.md)cmdlet to deploy specified policies for a Configuration Manager collection.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMUserDataAndProfileConfigurationItem](Get-CMUserDataAndProfileConfigurationItem)



* [Get-CMWindowsFirewallPolicy](Get-CMWindowsFirewallPolicy)



* [New-CMSchedule](New-CMSchedule)



* [New-CMConfigurationPolicyDeployment](New-CMConfigurationPolicyDeployment)





---


### Examples
#### Example 1: Create a configuration policy deployment
```PowerShell
PS XYZ:\> Set-CMConfigurationPolicyDeployment -CollectionName "Regional Remote Users" -FirewallPolicyName "Remote Firewall Policy"
```
This command creates a configuration policy deployment named Remote Firewall Policy and deploys it to the collection named Regional Remote Users.


---


### Parameters
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

Indicates whether to enable enforcement for the deployment. During enforcement, a client reports compliance information about a deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **FirewallPolicyId**

Specifies the ID of a Windows Firewall policy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **FirewallPolicyName**

Specifies the name of a Windows Firewall policy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases                                                                                               |
|-----------------|--------|--------|--------------|------------------------------------------------------------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|UserDataAndProfile<br/>FirewallPolicy<br/>RemoteConnectionProfile<br/>DeploymentSummary<br/>Assignment|



#### **MonitoredByScom**

Indicates whether System Center 2016 - Operations Manager monitoring criteria applies during the deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **OverrideServiceWindow**

Indicates whether to override the service window while deploying policies. Service windows are periods of time allocated for maintenance.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ParameterValue**

Specifies the values of administrator-defined parameters, such as thresholds. Configuration Manager stores the values in XML format.






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



#### **RemoteConnectionProfileId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RemoteConnectionProfileName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Schedule**

Specifies a schedule object. This is the schedule for deploying the configuration policy. You can use the New-CMSchedule (New-CMSchedule.md)cmdlet to create a schedule token.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **UserDataAndProfileId**

Specifies an ID of a user data and profile configuration item.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **UserDataAndProfileName**

Specifies a name of a user data and profile configuration item.






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
Set-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] -FirewallPolicyId <String> [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] -FirewallPolicyName <String> [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] -InputObject <IResultObject> [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDateTime <DateTime>] -RemoteConnectionProfileId <String> [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDateTime <DateTime>] -RemoteConnectionProfileName <String> [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] -UserDataAndProfileId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMConfigurationPolicyDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDateTime <DateTime>] [-Schedule <IResultObject>] -UserDataAndProfileName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
