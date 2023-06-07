Remove-CMClientSettingDeployment
--------------------------------




### Synopsis
Remove a specific deployment of a custom client setting.



---


### Description

Use this cmdlet to remove a specific deployment of a custom client setting. When you deploy custom settings, they override the default client settings. Custom client settings with a higher priority can also override other settings. For more information, see Create and deploy custom client settings (/mem/configmgr/core/clients/deploy/configure-client-settings#create-and-deploy-custom-client-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMClientSettingDeployment](Get-CMClientSettingDeployment)



* [New-CMClientSettingDeployment](New-CMClientSettingDeployment)



* [Get-CMClientSetting](Get-CMClientSetting)



* [Create and deploy custom client settings](Create and deploy custom client settings)





---


### Examples
#### Example 1: Remove a client setting deployment by ID
```PowerShell
$clientSettingId = (Get-CMClientSetting -Name "Remote control").SettingsID

Remove-CMClientSettingDeployment -CollectionID 'XYZ0003F' -ClientSettingsID $clientSettingId
```



---


### Parameters
#### **ClientSettingsId**

Specify the ID of the client settings that's deployed. This ID is the Settings ID in the console, and the SettingsID property on the SMS_ClientSettings WMI class.


You can use the Get-CMClientSetting (Get-CMClientSetting.md) cmdlet to get this property. For example, `(Get-CMClientSetting -Name "Remote control").SettingsID`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionId**

Specify the collection ID to which the client settings are deployed. This value is the standard collection ID format, for example, `XYZ00042`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a client settings deployment object to remove. To get this object, use the Get-CMClientSettingDeployment (Get-CMClientSettingDeployment.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Deployment|



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
Remove-CMClientSettingDeployment -ClientSettingsId <String> -CollectionId <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMClientSettingDeployment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
