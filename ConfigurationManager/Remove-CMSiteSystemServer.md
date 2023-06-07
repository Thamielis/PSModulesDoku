Remove-CMSiteSystemServer
-------------------------




### Synopsis
Remove the site system server role.



---


### Description

Use this cmdlet to remove the site system server role. A server with the Site system role hosts one or more other roles for a Configuration Manager site.



If the server has other site system roles besides the site system role, this cmdlet fails.



To remove other roles, use one of the following cmdlets:



- Remove-CMAssetIntelligenceSynchronizationPoint (Remove-CMAssetIntelligenceSynchronizationPoint.md)- Remove-CMCertificateRegistrationPoint (Remove-CMCertificateRegistrationPoint.md)- Remove-CMCloudManagementGatewayConnectionPoint (Remove-CMCloudManagementGatewayConnectionPoint.md)- Remove-CMDataWarehouseServicePoint (Remove-CMDataWarehouseServicePoint.md)- Remove-CMDistributionPoint (Remove-CMDistributionPoint.md)- Remove-CMEndpointProtectionPoint (Remove-CMEndpointProtectionPoint.md)- Remove-CMFallbackStatusPoint (Remove-CMFallbackStatusPoint.md)- Remove-CMManagementPoint (Remove-CMManagementPoint.md)- Remove-CMMulticastServicePoint (Remove-CMMulticastServicePoint.md)- Remove-CMReportingServicePoint (Remove-CMReportingServicePoint.md)- Remove-CMServiceConnectionPoint (Remove-CMServiceConnectionPoint.md)- Remove-CMSoftwareUpdatePoint (Remove-CMSoftwareUpdatePoint.md)- Remove-CMStateMigrationPoint (Remove-CMStateMigrationPoint.md)> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSiteSystemServer](Get-CMSiteSystemServer)



* [New-CMSiteSystemServer](New-CMSiteSystemServer)



* [Set-CMSiteSystemServer](Set-CMSiteSystemServer)





---


### Examples
#### Example 1: Remove a site system server
```PowerShell
Get-CMSiteSystemServer -SiteSystemServerName "Server2.contoso.com" -SiteCode "MP5" | Remove-CMSiteSystemServer -Force
```



---


### Parameters
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

Specify a site system server object to remove. To get this object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                        |
|-----------------|--------|--------|--------------|-------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteSystem<br/>SiteSystemServer|



#### **SiteCode**

Specify the Configuration Manager site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the name of the server with the site system role to remove.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



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
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMSiteSystemServer [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSiteSystemServer [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
