Get-CMClientSettingDeployment
-----------------------------




### Synopsis
Get a deployment of a custom client settings object.



---


### Description

Starting in version 2107, use this cmdlet to get a deployment of a custom client settings object. You can use this object with Remove-CMClientSettingDeployment (remove-cmclientsettingdeployment.md).



For more information on client settings, see How to configure client settings (/mem/configmgr/core/clients/deploy/configure-client-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMClientSettingDeployment](New-CMClientSettingDeployment)



* [Remove-CMClientSettingDeployment](Remove-CMClientSettingDeployment)



* [Get-CMClientSetting](Get-CMClientSetting)



* [Create and deploy custom client settings](Create and deploy custom client settings)





---


### Examples
#### Example 1: Get the deployment of a client setting by name
```PowerShell
$clientSetting =  Get-CMClientSetting -Name "Software Center customizations"
$clientSetting | Get-CMClientSettingDeployment
```



---


### Parameters
#### **Collection**

Specify a collection object to which the client settings object is deployed. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify the ID of a collection to which the client settings object is deployed. For example, `XYZ00012`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the name of a collection to which the client settings object is deployed.






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

Specify the ID of the client settings object that's deployed. The settings ID is an integer value, for example `47` or `16777225`.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|true    |named   |False        |ClientSettingsId|



#### **InputObject**

Specify a client settings object to get its deployments. To get this object, use the Get-CMClientSetting (Get-CMClientSetting.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases      |
|-----------------|--------|--------|--------------|-------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ClientSetting|



#### **Name**

Specify the name of the client settings object that's deployed.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |ClientSettingsName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_ClientSettingsAssignment


* IResultObject#SMS_ClientSettingsAssignment






---


### Notes
For more information on this return object and its properties, see SMS_ClientSettingsAssignment server WMI class (/mem/configmgr/develop/reference/core/clients/config/sms_clientsettingsassignment-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMClientSettingDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMClientSettingDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMClientSettingDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
