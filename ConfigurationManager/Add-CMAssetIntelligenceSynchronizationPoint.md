Add-CMAssetIntelligenceSynchronizationPoint
-------------------------------------------




### Synopsis
Installs an Asset Intelligence synchronization point.



---


### Description

The Add-CMAssetIntelligenceSynchronizationPoint cmdlet installs an Asset Intelligence synchronization point. Configuration Manager uses the Asset Intelligence synchronization point site system role to connect Configuration Manager sites to System Center Online to synchronize Asset Intelligence catalog information.



You can install the Asset Intelligence synchronization point only on a site system located at the top-level site of the Configuration Manager hierarchy.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAssetIntelligenceSynchronizationPoint](Get-CMAssetIntelligenceSynchronizationPoint)



* [New-CMSchedule](New-CMSchedule)



* [Remove-CMAssetIntelligenceSynchronizationPoint](Remove-CMAssetIntelligenceSynchronizationPoint)



* [Set-CMAssetIntelligenceSynchronizationPoint](Set-CMAssetIntelligenceSynchronizationPoint)





---


### Examples
#### Example 1: Install an Asset Intelligence synchronization point
```PowerShell
PS XYZ:\>Add-CMAssetIntelligenceSynchronizationPoint -SiteSystemServerName "CMDIV-TSQA04.CORP.CONTOSO.COM"
```
This command installs an Asset Intelligence synchronization point on the site system server named CMDIV-TSQA04.CORP.CONTOSO.COM.
#### Example 2: Install a scheduled Asset Intelligence synchronization point
```PowerShell
PS XYZ:\> $Sc = New-CMSchedule -DayOfWeek Friday -RecurCount 2
PS XYZ:\> Add-CMAssetIntelligenceSynchronizationPoint -SiteSystemServerName "CMDIV-TSQA04.CORP.CONTOSO.COM" -CertificateFile "\\Contoso01\CM\ACDataFile\AIpfx.pfx" -ScheduleToken $Sc
```
This first command creates a Configuration Manager schedule token that specifies an event that occurs once a week for three weeks on Fridays. The command stores the results in the $Sc variable.


The second command installs an Asset Intelligence synchronization point on the site system server named CMDIV-TSQA04.CORP.CONTOSO.COM, specifying the schedule stored in $Sc. The command also specifies the System Center Online authentication certificate (.pfx) file.


---


### Parameters
#### **CertificateFile**

Specifies the path to a System Center Online authentication certificate (.pfx) file.






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



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteServer|



#### **Schedule**

Specifies a CMSchedule object. The schedule specifies when the maintenance window occurs. To create a CMSchedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases      |
|-----------------|--------|--------|-------------|-------------|
|`[IResultObject]`|false   |named   |False        |ScheduleToken|



#### **SiteSystemServerName**

Specifies an array of fully qualified domain names (FQDN) of the servers that host the site system role.






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
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Add-CMAssetIntelligenceSynchronizationPoint [-CertificateFile <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMAssetIntelligenceSynchronizationPoint [-SiteSystemServerName] <String> [-CertificateFile <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
