Set-CMMulticastServicePoint
---------------------------




### Synopsis
Sets a multicast service point.



---


### Description

The Set-CMMulticastServicePoint cmdlet updates the configuration of multicast settings for a distribution point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMMulticastServicePoint](Add-CMMulticastServicePoint)



* [Get-CMMulticastServicePoint](Get-CMMulticastServicePoint)



* [Remove-CMMulticastServicePoint](Remove-CMMulticastServicePoint)





---


### Examples
#### Example 1: Modify a multicast service point by using the pipeline
```PowerShell
PS XYZ:\> Get-CMMulticastServicePoint -SiteSystemServerName "server01.contoso.com" | Set-CMMulticastServicePoint -UserName $null -StartIPAddress 224.0.1.0 -EndIPAddress 239.255.255.255 -StartUdpPort 64001 -EndUdpPort 65000 -ClientTransferRate Profile100Mbps -MaximumClientCount 100 -EnableScheduledMulticast $true -SessionStartDelayMins 15 -MinimumClientCount 20
```
This command gets the multicast service point object with the site system server name server1.contoso.com and uses the pipeline operator to pass the object to Set-CMMulticastServicePoint . Set-CMMulticastServicePoint updates the multicast settings on the distribution point object by creating an IP address range of 224.0.1.0 to 239.255.255.255, and a UDP port range of 64001 to 65000. The command also sets the minimum and maximum client count, and sets a start delay of 15 minutes.
#### Example 2: Modify a multicast service point
```PowerShell
PS XYZ:\> Set-CMMulticastServicePoint -SiteSystemServerName "server02.contoso.com" -UserName "contoso\administrator" -StartIPAddress 224.0.1.0 -EndIPAddress 239.255.255.255 -StartUdpPort 64001 -EndUdpPort 65000 -ClientTransferRate "Profile100Mbps" -MaximumClientCount 100 -EnableScheduledMulticast $true -SessionStartDelayMins 15 -MinimumClientCount 20
```
This command updates the multicast service point settings for the site system server named server1.contoso.com using the administrator account. The command creates an IP address range of 224.0.1.0 to 239.255.255.255, and a UDP port range of 64001 to 65000. The command also sets the minimum and maximum client count, and sets a start delay of 15 minutes.


---


### Parameters
#### **ClientTransferRate**

No longer used. Transfer speed is dynamic.


Specifies the client transfer rate. Valid values are:


* None


* Profile100Mbps


* Profile10Mbps


* Profile1Gbps


* ProfileCustom



Valid Values:

* None
* ProfileCustom
* Profile10Mbps
* Profile100Mbps
* Profile1Gbps






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[NetworkProfile]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableScheduledMulticast**

Indicates whether you can schedule when Configuration Manager deploys the operating system image from the distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EndIPAddress**

Specifies the ending IP address in the range of IP addresses that Configuration Manager uses to send data to the destination computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **EndUdpPort**

Specifies the ending port in the range of user datagram protocol (UDP) ports that Configuration Manager uses to send data to the destination computers.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a multicast service point object. To obtain a multicast service point object, use the Get-CMMulticastServicePoint (Get-CMMulticastServicePoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases              |
|-----------------|--------|--------|--------------|---------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|MulticastServicePoint|



#### **MaximumClientCount**

Specifies the maximum number of destination computers that can download the operating system from this distribution point.






|Type     |Required|Position|PipelineInput|Aliases                    |
|---------|--------|--------|-------------|---------------------------|
|`[Int32]`|false   |named   |False        |MulticastMaximumClientCount|



#### **MinimumClientCount**

Specifies the minimum number of requests that must be received before Configuration Manager starts to deploy the operating system.






|Type     |Required|Position|PipelineInput|Aliases           |
|---------|--------|--------|-------------|------------------|
|`[Int32]`|false   |named   |False        |MinimumSessionSize|



#### **PassThru**

Returns an object that represents the multicast service point. By default, this cmdlet does not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SessionStartDelayMins**

Specifies the number of minutes that Configuration Manager waits before it responds to the first deployment request.






|Type     |Required|Position|PipelineInput|Aliases                 |
|---------|--------|--------|-------------|------------------------|
|`[Int32]`|false   |named   |False        |SessionStartDelayMinutes|



#### **SiteCode**

Specifies the site code for the Configuration Manager site that hosts the site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of the server that hosts a site system role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **StartIPAddress**

Specifies the starting IP address in the range of IP addresses that Configuration Manager uses to send data to the destination computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StartUdpPort**

Specifies the starting port in the range of UDP ports that Configuration Manager uses to send data to the destination computers.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UseAnyRangeIP**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UserName**

Specifies the name of the user that the distribution site system components use to connect to the primary site database. If the UserName parameter is not specified, the cmdlet uses the computer account of the distribution point to the primary site database.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Set-CMMulticastServicePoint [-InputObject] <IResultObject> [-ClientTransferRate {None | ProfileCustom | Profile10Mbps | Profile100Mbps | Profile1Gbps}] [-DisableWildcardHandling] [-EnableScheduledMulticast <Boolean>] [-EndIPAddress <String>] [-EndUdpPort <Int32>] [-ForceWildcardHandling] [-MaximumClientCount <Int32>] [-MinimumClientCount <Int32>] [-PassThru] [-SessionStartDelayMins <Int32>] [-StartIPAddress <String>] [-StartUdpPort <Int32>] [-UseAnyRangeIP] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMulticastServicePoint [-SiteSystemServerName] <String> [-ClientTransferRate {None | ProfileCustom | Profile10Mbps | Profile100Mbps | Profile1Gbps}] [-DisableWildcardHandling] [-EnableScheduledMulticast <Boolean>] [-EndIPAddress <String>] [-EndUdpPort <Int32>] [-ForceWildcardHandling] [-MaximumClientCount <Int32>] [-MinimumClientCount <Int32>] [-PassThru] [-SessionStartDelayMins <Int32>] [-SiteCode <String>] [-StartIPAddress <String>] [-StartUdpPort <Int32>] [-UseAnyRangeIP] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
