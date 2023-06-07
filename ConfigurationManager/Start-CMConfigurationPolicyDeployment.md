Start-CMConfigurationPolicyDeployment
-------------------------------------




### Synopsis
(Deprecated) Deploys policies for a Configuration Manager collection.



---


### Description

> [!IMPORTANT] > This cmdlet is deprecated. Use New-CMConfigurationPolicyDeployment (New-CMConfigurationPolicyDeployment.md)instead.



The Start-CMConfigurationPolicyDeployment cmdlet deploys specified policies for a Configuration Manager collection. You can deploy firewall policies or user session management policies.



You can specify a firewall policy by name or by ID or use another cmdlet to get firewall policy object.



You can specify System Center 2016 - Operations Manager monitoring criteria.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMConfigurationPolicyDeployment](Set-CMConfigurationPolicyDeployment)





---


### Examples
#### Example 1: Start deployment of a firewall policy
```PowerShell
PS XYZ:\> Start-CMConfigurationPolicyDeployment -CollectionName "Desktop systems" -FirewallPolicyName "General firewall policy"
```
This command starts the configuration policy deployment for a collection named Desktop systems. The command specifies a firewall policy named General firewall policy.


---


### Parameters
#### **CollectionName**

Specifies the name of a collection. The deployment applies to this Configuration Manager collection.






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



#### **FirewallPolicy**

Specifies a firewall policy object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **FirewallPolicyId**

Specifies an ID for a firewall policy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **FirewallPolicyName**

Specifies a name for a firewall policy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **MonitoredByScom**

Specifies whether Operations Manager monitoring criteria applies during the deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **OverrideServiceWindow**

Specifies whether to override the service window while deploying policies.






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



#### **PostponeDate**

Specifies a date, as a DateTime object. To get a DateTime object, use the Get-Date cmdlet. For more information, type `Get-Help Get-Date`. This is the date for the deployment if postponed.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **PostponeTime**

Specifies a time, as a DateTime object. To obtain a DateTime object, use the Get-Date cmdlet. This is the time for the deployment if postponed.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **RemoteConnectionProfile**

Specifies the remote connection profile that this cmdlet deploys configuration policy on.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **RemoteConnectionProfileId**

Specifies the remote connection profile ID that this cmdlet deploys configuration policy for.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RemoteConnectionProfileName**

Specifies the remote connection profile name that this cmdlet deploys configuration policy for.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Schedule**

Specifies a schedule object. This is the schedule for evaluating the policy.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **UserDataAndProfile**

Specifies a user data and profile object. To obtain a user data and profile object, use the Get-CMUserDataAndProfileConfigurationItem cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **UserDataAndProfileId**

Specifies an ID for a user data and profile object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **UserDataAndProfileName**

Specifies a name for a user data and profile object.






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
Start-CMConfigurationPolicyDeployment -CollectionName <String> [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDate <DateTime>] [-PostponeTime <DateTime>] [-Schedule <IResultObject>] -UserDataAndProfileId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMConfigurationPolicyDeployment -CollectionName <String> [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDate <DateTime>] [-PostponeTime <DateTime>] [-Schedule <IResultObject>] -UserDataAndProfileName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMConfigurationPolicyDeployment -CollectionName <String> [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDate <DateTime>] [-PostponeTime <DateTime>] [-Schedule <IResultObject>] -UserDataAndProfile <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMConfigurationPolicyDeployment -CollectionName <String> [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDate <DateTime>] [-PostponeTime <DateTime>] -RemoteConnectionProfileId <String> [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMConfigurationPolicyDeployment -CollectionName <String> [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDate <DateTime>] [-PostponeTime <DateTime>] -RemoteConnectionProfileName <String> [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMConfigurationPolicyDeployment -CollectionName <String> [-DisableWildcardHandling] [-EnableEnforcement <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-MonitoredByScom <Boolean>] [-OverrideServiceWindow <Boolean>] [-ParameterValue <Int32>] [-PassThru] [-PostponeDate <DateTime>] [-PostponeTime <DateTime>] -RemoteConnectionProfile <IResultObject> [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMConfigurationPolicyDeployment -CollectionName <String> [-DisableWildcardHandling] -FirewallPolicy <IResultObject> [-ForceWildcardHandling] [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMConfigurationPolicyDeployment -CollectionName <String> [-DisableWildcardHandling] -FirewallPolicyId <String> [-ForceWildcardHandling] [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMConfigurationPolicyDeployment -CollectionName <String> [-DisableWildcardHandling] -FirewallPolicyName <String> [-ForceWildcardHandling] [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
