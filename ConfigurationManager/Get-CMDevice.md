Get-CMDevice
------------




### Synopsis
Get a Configuration Manager device.



---


### Description

The Get-CMDevice cmdlet gets a Configuration Manager device. By default it queries the SMS_CM_RES_COLL_SMS00001 class. You can use the Resource or CollectionMember parameters to change the query class. Depending upon your role-based access in the site, you may need to use one of these other parameters. For example, if you don't have access to SMS00001, then by default this cmdlet returns zero results.<!-- 12549811 -->



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMResource](Get-CMResource)



* [Approve-CMDevice](Approve-CMDevice)



* [Block-CMDevice](Block-CMDevice)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Remove-CMDevice](Remove-CMDevice)



* [Unblock-CMDevice](Unblock-CMDevice)





---


### Examples
#### Example 1: Get devices by collection ID
```PowerShell
Get-CMDevice -CollectionID "XYZ0004B" | Select-Object Name, ClientVersion, DeviceOS, IsActive, LastActiveTime, LastClientCheckTime, LastDDR, LastHardwareScan, LastPolicyRequest

Name                : DEVICE-LT3
ClientVersion       : 5.00.9012.1020
DeviceOS            : Microsoft Windows NT Workstation 10.0 (Tablet Edition)
IsActive            : True
LastActiveTime      : 10/1/2020 23:29:34
LastClientCheckTime : 9/8/2020 18:38:10
LastDDR             : 9/30/2020 20:29:33
LastHardwareScan    : 9/30/2020 22:24:22
LastPolicyRequest   : 10/1/2020 23:29:34

Name                : DEVICE-LT2
ClientVersion       : 5.00.9030.1011
DeviceOS            : Microsoft Windows NT Workstation 10.0 (Tablet Edition)
IsActive            : True
LastActiveTime      : 10/2/2020 00:31:54
LastClientCheckTime : 9/30/2020 23:06:10
LastDDR             : 9/30/2020 19:44:46
LastHardwareScan    : 9/30/2020 01:15:52
LastPolicyRequest   : 10/2/2020 00:31:54
```

#### Example 2: Get device resources by collection ID
```PowerShell
Get-CMDevice -CollectionID "XYZ0004B" -Resource | Select-Object Name, ClientVersion, OperatingSystemNameandVersion, Active, AgentName, AgentTime

Name                          : DEVICE-LT3
ClientVersion                 : 5.00.9012.1020
OperatingSystemNameandVersion : Microsoft Windows NT Workstation 10.0 (Tablet Edition)
Active                        : 1
AgentName                     : {SMS_AD_SYSTEM_DISCOVERY_AGENT, SMS_AD_SECURITY_GROUP_DISCOVERY_AGENT,
                                MP_ClientRegistration, Heartbeat Discovery}
AgentTime                     : {2/28/2020 09:45:01, 10/2/2020 01:00:01, 9/21/2020 15:53:47, 9/30/2020 13:29:33}

Name                          : DEVICE-LT2
ClientVersion                 : 5.00.9030.1011
OperatingSystemNameandVersion : Microsoft Windows NT Workstation 10.0 (Tablet Edition)
Active                        : 1
AgentName                     : {SMS_AD_SYSTEM_DISCOVERY_AGENT, SMS_AD_SECURITY_GROUP_DISCOVERY_AGENT,
                                MP_ClientRegistration, Heartbeat Discovery}
AgentTime                     : {2/28/2020 09:45:01, 10/2/2020 01:00:01, 10/1/2020 14:03:56, 9/30/2020 12:44:46}
```

#### Example 3: Get properties for a specific device
```PowerShell
Get-CMDevice -Name "DEVICE-LT2" -Resource | Select-Object Name, CPUType, DistinguishedName, HardwareID, IPAddresses
```

#### Example 4: Get devices that aren't clients
```PowerShell
Get-CMDevice -Fast | Where-Object { $_.IsClient -eq $false } | Select-Object Name
```

#### Example 5: Get devices for a specific threat name
```PowerShell
Get-CMDevice -ThreatName "Trojan:Win32/Wacatac.B!ml" | Select-Object Name
```

#### Example 6: Get all devices with any detected malware
```PowerShell
$allMalware = Get-CMDetectedMalware
foreach ( $malware in $allMalware ) { Get-CMDevice -InputObject $malware | Select-Object Name }
```



---


### Parameters
#### **Collection**

Use this parameter to get all devices from a device collection object. To get this object, use the Get-CMDeviceCollection (Get-CMDeviceCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **CollectionId**

Specify an ID for a device collection. For example, `XYZ0004B`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionMember**

Add this parameter to query the SMS_R_UnknownSystem and SMS_R_System classes for device information. These classes may be restricted by role-based access. These classes contain more detailed machine information.






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[Switch]`|false   |named   |False        |CollectionMemberInstance|



#### **CollectionName**

Specify the name of a device collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a detected malware object. To get this object, use the Get-CMDetectedMalware (Get-CMDetectedMalware.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Threat |



#### **Name**

Specify the name of a device.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Resource**

Add this parameter to query the SMS_Resource class for device information. This class shouldn't be restricted by role-based access. The output is the same as with the Get-CMResource cmdlet. This output has minimal properties for the device. For more detailed properties, don't add this parameter, or use the CollectionMember parameter.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[Switch]`|false   |named   |False        |ResourceInstance|



#### **ResourceId**

Specify the resource ID of a device. For example, `16780010`.






|Type     |Required|Position|PipelineInput|Aliases        |
|---------|--------|--------|-------------|---------------|
|`[Int32]`|true    |named   |False        |Id<br/>DeviceId|



#### **ThreatId**

Use this parameter to filter the devices that it returns to those devices with specific malware by ID. For example, `2147735505`. To get this threat ID, use the Get-CMDetectedMalware (Get-CMDetectedMalware.md)cmdlet.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |ThreatNameId|



#### **ThreatName**

Use this parameter to filter the devices that it returns to those devices with specific malware by name. For example, `Trojan:Win32/Wacatac.B!ml`. To get this threat name, use the Get-CMDetectedMalware (Get-CMDetectedMalware.md)cmdlet.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_CombinedDeviceResources


* IResultObject#SMS_CombinedDeviceResources






---


### Notes
For more information on this return object and its properties, see SMS_CombinedDeviceResources server WMI class (/mem/configmgr/develop/reference/core/clients/collections/sms_combineddeviceresources-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMDevice -Collection <IResultObject> [-CollectionMember] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [-Resource] [<CommonParameters>]
```
```PowerShell
Get-CMDevice -CollectionId <String> [-CollectionMember] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [-Resource] [<CommonParameters>]
```
```PowerShell
Get-CMDevice [-CollectionId <String>] [-CollectionMember] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Resource] -ThreatId <String> [<CommonParameters>]
```
```PowerShell
Get-CMDevice [-CollectionId <String>] [-CollectionMember] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Resource] -ThreatName <String> [<CommonParameters>]
```
```PowerShell
Get-CMDevice [-CollectionId <String>] [-CollectionMember] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -InputObject <IResultObject> [-Resource] [<CommonParameters>]
```
```PowerShell
Get-CMDevice [-CollectionMember] -CollectionName <String> [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [-Resource] [<CommonParameters>]
```
```PowerShell
Get-CMDevice [-CollectionMember] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [-Resource] [<CommonParameters>]
```
```PowerShell
Get-CMDevice [-CollectionMember] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Resource] -ResourceId <Int32> [<CommonParameters>]
```
