New-CMTSNetworkAdapterSetting
-----------------------------




### Synopsis
Create a settings object for a network adapter on the Apply Network Settings task sequence step.



---


### Description

This cmdlet creates a network adapter settings object. Use this object with the AddAdapterSetting parameter on the New-CMTSStepApplyNetworkSetting (New-CMTSStepApplyNetworkSetting.md) or [Set-CMTSStepApplyNetworkSetting](Set-CMTSStepApplyNetworkSetting.md)cmdlets.



For more information, see About task sequence steps: Apply Network Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyNetworkSettings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTSStepApplyNetworkSetting](New-CMTSStepApplyNetworkSetting)



* [Set-CMTSStepApplyNetworkSetting](Set-CMTSStepApplyNetworkSetting)



* [About task sequence steps: Apply Network Settings](About task sequence steps: Apply Network Settings)





---


### Examples
#### Example 1: Add network adapter settings for a connection with multiple addresses
```PowerShell
$dns = @("192.168.1.100","10.0.1.100")
$gw = @("192.168.1.1","10.0.1.1")

$ip = @(
    @{ IP = "192.168.1.42"; Mask = "255.255.255.0"; },
    @{ IP = "10.0.1.42"; Mask = "255.255.242.0"; }
)

$conn1 = New-CMTSNetworkAdapterSetting -Name "local connection" -Dns $dns -EnableDnsRegistration -EnableFullDnsRegistration -Gateway $gw -IpAddress $ip -TcpIpNetbiosOption DisableNetbiosOverTcpip

$tsNameOsd = "Default OS deployment"
$tsStepNameApplyNetSet = "Apply Network Settings"

Set-CMTSStepApplyNetworkSetting -TaskSequenceName $tsNameOsd -StepName $tsStepNameApplyNetSet -AddAdapterSetting $conn1 -DnsSuffix "corp.contoso.com"
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Dns**

Specify one or more DNS server addresses in order of use.






|Type        |Required|Position|PipelineInput|Aliases                                |
|------------|--------|--------|-------------|---------------------------------------|
|`[String[]]`|false   |named   |False        |DNSServerAddress<br/>DNSServerAddresses|



#### **EnableDnsRegistration**

Add this parameter to register this connection's addresses in DNS. This setting applies to all connections with TCP/IP enabled. To specify the DNS suffix, use the DnsSuffix parameter on the New-CMTSStepApplyNetworkSetting (New-CMTSStepApplyNetworkSetting.md) or [Set-CMTSStepApplyNetworkSetting](Set-CMTSStepApplyNetworkSetting.md)cmdlets.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableFullDnsRegistration**

Add this parameter to use the connection's DNS suffix in DNS registration. This setting applies to all connections with TCP/IP enabled. To specify the DNS suffix, use the DnsSuffix parameter on the New-CMTSStepApplyNetworkSetting (New-CMTSStepApplyNetworkSetting.md) or [Set-CMTSStepApplyNetworkSetting](Set-CMTSStepApplyNetworkSetting.md)cmdlets.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableIpProtocolFiltering**

Add this parameter to filter some IP protocols. To enable TCP/IP filtering, use the EnableTcpIpFiltering parameter on the New-CMTSStepApplyNetworkSetting (New-CMTSStepApplyNetworkSetting.md) or [Set-CMTSStepApplyNetworkSetting](Set-CMTSStepApplyNetworkSetting.md)cmdlets.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableLmHosts**

Add this parameter to enable LMHOSTS lookup.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableTcpFiltering**

Add this parameter to filter some TCP ports. To enable TCP/IP filtering, use the EnableTcpIpFiltering parameter on the New-CMTSStepApplyNetworkSetting (New-CMTSStepApplyNetworkSetting.md) or [Set-CMTSStepApplyNetworkSetting](Set-CMTSStepApplyNetworkSetting.md)cmdlets.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableUdpFiltering**

Add this parameter to filter some UDP ports. To enable TCP/IP filtering, use the EnableTcpIpFiltering parameter on the New-CMTSStepApplyNetworkSetting (New-CMTSStepApplyNetworkSetting.md) or [Set-CMTSStepApplyNetworkSetting](Set-CMTSStepApplyNetworkSetting.md)cmdlets.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Gateway**

If this connection doesn't use DHCP, use this parameter to specify one or more gateway addresses.


If needed, use the Metric parameter. By default, the gateway uses an automatic metric.






|Type        |Required|Position|PipelineInput|Aliases                                |
|------------|--------|--------|-------------|---------------------------------------|
|`[String[]]`|false   |named   |False        |GatewayIpAddress<br/>GatewayIpAddresses|



#### **IpAddress**

If this connection doesn't use DHCP, use this parameter to specify one or more IP addresses and corresponding subnet masks. The value is a hashtable. The first value is the `IP` and the second value is the `Mask`.


For example: `@{ IP = "192.168.1.42"; Mask = "255.255.255.0"; }`


If you need to specify more than one IP address and subnet mask combination, use an array of hashtables.


For example: `@( @{ IP = "192.168.1.42"; Mask = "255.255.255.0"; }, @{ IP = "10.0.1.42"; Mask = "255.255.242.0"; } )`






|Type           |Required|Position|PipelineInput|Aliases                                              |
|---------------|--------|--------|-------------|-----------------------------------------------------|
|`[Hashtable[]]`|false   |named   |False        |NetworkSettingIpAddress<br/>NetworkSettingIpAddresses|



#### **IpProtocolFilterList**

When you use the EnableIpProtocolFiltering parameter, use this parameter to specify one or more IP protocols.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **Metric**

Specify the metric that indicates the cost of using the Gateway . If you don't specify this parameter, the gateway uses an automatic metric.






|Type     |Required|Position|PipelineInput|Aliases          |
|---------|--------|--------|-------------|-----------------|
|`[Int32]`|false   |named   |False        |GatewayCostMetric|



#### **Name**

Specify a unique name for this connection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TcpFilterPortList**

When you use the EnableTcpFiltering parameter, use this parameter to specify one or more TCP ports.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Int32[]]`|false   |named   |False        |



#### **TcpIpNetbiosOption**

Specify whether to enable or disable NetBIOS over TCP/IP.



Valid Values:

* Default
* EnableNetbiosOverTcpip
* DisableNetbiosOverTcpip






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[NetbiosOption]`|false   |named   |False        |



#### **UdpFilterPortList**

When you use the EnableUdpFiltering parameter, use this parameter to specify one or more UDP ports.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Int32[]]`|false   |named   |False        |



#### **Wins**

Specify one or more WINS server addresses.






|Type        |Required|Position|PipelineInput|Aliases                                  |
|------------|--------|--------|-------------|-----------------------------------------|
|`[String[]]`|false   |named   |False        |WinsServerAddress<br/>WinsServerAddresses|



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
None





---


### Outputs
* IResultObject#SMS_TaskSequence_NetworkAdapterSettings






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_NetworkAdapterSettings server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_networkadaptersettings-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSNetworkAdapterSetting [-DisableWildcardHandling] [-Dns <String[]>] [-EnableDnsRegistration] [-EnableFullDnsRegistration] [-EnableIpProtocolFiltering] [-EnableLmHosts] [-EnableTcpFiltering] [-EnableUdpFiltering] [-ForceWildcardHandling] [-Gateway <String[]>] [-IpAddress <Hashtable[]>] [-IpProtocolFilterList <String[]>] [-Metric <Int32>] -Name <String> [-TcpFilterPortList <Int32[]>] [-TcpIpNetbiosOption {Default | EnableNetbiosOverTcpip | DisableNetbiosOverTcpip}] [-UdpFilterPortList <Int32[]>] [-Wins <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
