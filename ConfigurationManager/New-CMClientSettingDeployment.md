New-CMClientSettingDeployment
-----------------------------




### Synopsis
Deploy a custom client setting.



---


### Description

Use this cmdlet to deploy a custom client setting. When you deploy custom settings, they override the default client settings. Custom client settings with a higher priority can also override other settings. For more information, see Create and deploy custom client settings (/mem/configmgr/core/clients/deploy/configure-client-settings#create-and-deploy-custom-client-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMClientSettingDeployment](Get-CMClientSettingDeployment)



* [Remove-CMClientSettingDeployment](Remove-CMClientSettingDeployment)



* [Get-CMClientSetting](Get-CMClientSetting)



* [Create and deploy custom client settings](Create and deploy custom client settings)





---


### Examples
#### Example 1: Deploy a client setting object by using its ID to a named collection
```PowerShell
New-CMClientSettingDeployment -Id "16777225" -CollectionName "General Computer Collection"
```



---


### Parameters
#### **Collection**

Specify a collection object as the target for the deployment. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify an ID for the collection to target this deployment. This value is a standard collection ID, for example, `XYZ00042`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify a collection name to target this deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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

Specify the ID of the custom client settings to deploy. This ID is the Settings ID in the console, and the SettingsID property on the SMS_ClientSettings WMI class.


You can use the Get-CMClientSetting (Get-CMClientSetting.md) cmdlet to get this property. For example, `(Get-CMClientSetting -Name "Remote control").SettingsID`






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|true    |named   |False        |ClientSettingId|



#### **InputObject**

Specify a custom client settings object to deploy. To get this object, use the Get-CMClientSetting (Get-CMClientSetting.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases      |
|-----------------|--------|--------|--------------|-------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ClientSetting|



#### **Name**

Specify the name of the custom client settings to deploy.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|true    |named   |False        |ClientSettingName|



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
New-CMClientSettingDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMClientSettingDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMClientSettingDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
