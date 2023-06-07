Start-CMClientSettingDeployment
-------------------------------




### Synopsis
(Deprecated) Deploys client settings to devices in a collection.



---


### Description

The Start-CMClientSettingDeployment cmdlet deploys client settings to devices in a Configuration Manager collection. Specify the client setting object by using its name or ID, or you can use the Get-CMClientSetting cmdlet to get a client setting object. Specify the collection to apply the settings to by using its name or ID, or you can use the Get-CMDeviceCollection (Get-CMDeviceCollection.md)cmdlet to get a device collection.



For more information about client settings, see About Client Settings in Configuration Manager (/mem/configmgr/core/clients/deploy/about-client-settings).



> [!IMPORTANT] > Starting in version 2107, this cmdlet is deprecated and may be removed in a future release. Instead use the New-CMClientSettingDeployment (New-CMClientSettingDeployment.md)cmdlet.



---


### Related Links
* [Get-CMClientSetting](Get-CMClientSetting)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)





---


### Examples
#### Example 1: Deploy a client setting object by using its ID to a named collection
```PowerShell
PS XYZ:\> Start-CMClientSettingDeployment -ClientSettingId "CSI1023" -CollectionName "General Computer Collection"
```
This command starts deployment of the client setting object that has the ID CSI1023 for the collection named General Computer Collection.
#### Example 2: Deploy a client setting object by using a variable
```PowerShell
PS XYZ:\> $CSID = Get-CMClientSetting -Id "CSI1023"
PS XYZ:\> Start-CMClientSettingDeployment -ClientSetting $CSID -CollectionName "General Computer Collection"
```
The first command gets a client setting object that has the ID CSI1023, and saves it in the $CSID variable.


The second command starts deployment of the client setting object in the $CSID variable to the collection named General Computer Collection.


---


### Parameters
#### **ClientSetting**

Specifies a client setting object. To obtain a client setting object, use the Get-CMClientSetting (Get-CMClientSetting.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **ClientSettingId**

Specifies the ID of a client setting object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ClientSettingName**

Specifies the name of a client setting object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Collection**

Specifies a Configuration Manager collection object. To obtain a collection object, use the Get-CMDeviceCollection (Get-CMDeviceCollection.md)cmdlet. Configuration Manager applies the client settings to the members of this collection.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **CollectionId**

Specifies the ID of a Configuration Manager collection. Configuration Manager applies the client settings to the members of this collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specifies the name of a Configuration Manager collection. Configuration Manager applies the client settings to the members of this collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Start-CMClientSettingDeployment -ClientSetting <IResultObject> -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMClientSettingDeployment -ClientSetting <IResultObject> -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMClientSettingDeployment -ClientSetting <IResultObject> -Collection <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMClientSettingDeployment -ClientSettingId <String> -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMClientSettingDeployment -ClientSettingId <String> -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMClientSettingDeployment -ClientSettingId <String> -Collection <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMClientSettingDeployment -ClientSettingName <String> -Collection <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMClientSettingDeployment -ClientSettingName <String> -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMClientSettingDeployment -ClientSettingName <String> -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
