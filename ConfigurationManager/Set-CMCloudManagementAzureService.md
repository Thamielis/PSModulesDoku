Set-CMCloudManagementAzureService
---------------------------------




### Synopsis
Modify the settings of the Azure service for Cloud Management in Configuration Manager.



---


### Description

Use this cmdlet to modify the settings of an Azure service in Configuration Manager for Cloud Management .



For more information about the Cloud Management service, see CMG Overview (/mem/configmgr/core/clients/manage/cmg/overview).



---


### Related Links
* [Import-CMAADServerApplication](Import-CMAADServerApplication)



* [Import-CMAADClientApplication](Import-CMAADClientApplication)



* [New-CMCloudManagementAzureService](New-CMCloudManagementAzureService)



* [New-CMCloudManagementGateway](New-CMCloudManagementGateway)



* [Add-CMCloudManagementGatewayConnectionPoint](Add-CMCloudManagementGatewayConnectionPoint)



* [CMG Overview](CMG Overview)





---


### Examples
#### Example 1
```PowerShell
Get-CMAzureService -Name "Contoso" | Set-CMCloudManagementAzureService -NewName "CMG service" -Description "ConfigMgr connection to Contoso tenant for CMG"
```



---


### Parameters
#### **AddGroupName**

Specify an Azure Active Directory (Azure AD) group name to discover. Use this parameter with the EnableGroupDiscovery parameter.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |AddGroupNames|



#### **DeleteGroupName**

Specify an Azure AD group name to remove from discovery.






|Type        |Required|Position|PipelineInput|Aliases         |
|------------|--------|--------|-------------|----------------|
|`[String[]]`|false   |named   |False        |DeleteGroupNames|



#### **Description**

Specify an optional description for the service.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableAADGroupSync**

Enable Configuration Manager to sync collections to groups in Azure AD. For more information, see Synchronize members to Azure AD groups (/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_aadcollsync).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableGroupDeltaDiscovery**

Set this parameter to `true` to enable delta discovery for Azure AD group discovery. Use this parameter with the EnableGroupDiscovery parameter. Use the GroupDeltaDiscoveryMins parameter to configure the delta discovery interval.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableGroupDiscovery**

Set this parameter to `true` to enable Azure AD group discovery. When you enable this discovery method, also configure the following parameters:


* AddGroupName : Add Azure AD groups to discover - EnableGroupDeltaDiscovery : Configure delta discovery - GroupDeltaDiscoveryMins : Delta discovery interval - GroupDiscoverySchedule : Full polling schedule


For more information on this discovery method, see Azure Active Directory user group discovery (/mem/configmgr/core/servers/deploy/configure/about-discovery-methods#bkmk_azuregroupdisco).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUserDeltaDiscovery**

Set this parameter to `true` to enable delta discovery for Azure AD user discovery. Use this parameter with the EnableUserDiscovery parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUserDiscovery**

Set this parameter to `true` to enable Azure AD user discovery. When you enable this discovery method, also configure the following parameters:


* EnableUserDeltaDiscovery : Configure delta discovery - UserDeltaDiscoveryMins : Delta discovery interval - UserDiscoverySchedule : Full polling schedule


For more information on this discovery method, see Azure Active Directory user discovery (/mem/configmgr/core/servers/deploy/configure/about-discovery-methods#azureaddisc).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GroupDeltaDiscoveryMins**

When you enable delta discovery for Azure AD group discovery with the EnableGroupDeltaDiscovery parameter, use this parameter to configure the delta discovery interval. The integer value you specify is the polling interval in minutes.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **GroupDiscoverySchedule**

Specify a schedule object for the Azure AD group discovery full polling schedule. To get this object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **Id**

Specify the site's ID for the Azure service. The Id is the integer value stored in the site database for the service. For example, run the following SQL query, and look at the ID column: `select * from Azure_CloudService`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |AzureServiceId|



#### **InputObject**

Specify an Azure service object to configure. To get this object, use the Get-CMAzureService (Get-CMAzureService.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|AzureService|



#### **Name**

Specify a name to distinguish the Cloud Management service in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|true    |named   |False        |AzureServiceName|



#### **NewName**

Use this parameter to rename the Cloud Management service in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UserDeltaDiscoveryMins**

When you enable delta discovery for Azure AD user discovery with the EnableUserDeltaDiscovery parameter, use this parameter to configure the delta discovery interval. The integer value you specify is the polling interval in minutes.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UserDiscoverySchedule**

Specify a schedule object for the Azure AD user discovery full polling schedule. To get this object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






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
Set-CMCloudManagementAzureService [-AddGroupName <String[]>] [-DeleteGroupName <String[]>] [-Description <String>] [-DisableWildcardHandling] [-EnableAADGroupSync <Boolean>] [-EnableGroupDeltaDiscovery <Boolean>] [-EnableGroupDiscovery <Boolean>] [-EnableUserDeltaDiscovery <Boolean>] [-EnableUserDiscovery <Boolean>] [-ForceWildcardHandling] [-GroupDeltaDiscoveryMins <Int32>] [-GroupDiscoverySchedule <IResultObject>] -Id <Int32> [-NewName <String>] [-PassThru] [-UserDeltaDiscoveryMins <Int32>] [-UserDiscoverySchedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCloudManagementAzureService [-AddGroupName <String[]>] [-DeleteGroupName <String[]>] [-Description <String>] [-DisableWildcardHandling] [-EnableAADGroupSync <Boolean>] [-EnableGroupDeltaDiscovery <Boolean>] [-EnableGroupDiscovery <Boolean>] [-EnableUserDeltaDiscovery <Boolean>] [-EnableUserDiscovery <Boolean>] [-ForceWildcardHandling] [-GroupDeltaDiscoveryMins <Int32>] [-GroupDiscoverySchedule <IResultObject>] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-UserDeltaDiscoveryMins <Int32>] [-UserDiscoverySchedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCloudManagementAzureService [-AddGroupName <String[]>] [-DeleteGroupName <String[]>] [-Description <String>] [-DisableWildcardHandling] [-EnableAADGroupSync <Boolean>] [-EnableGroupDeltaDiscovery <Boolean>] [-EnableGroupDiscovery <Boolean>] [-EnableUserDeltaDiscovery <Boolean>] [-EnableUserDiscovery <Boolean>] [-ForceWildcardHandling] [-GroupDeltaDiscoveryMins <Int32>] [-GroupDiscoverySchedule <IResultObject>] -Name <String> [-NewName <String>] [-PassThru] [-UserDeltaDiscoveryMins <Int32>] [-UserDiscoverySchedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
