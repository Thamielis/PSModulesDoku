Set-CMAssetIntelligenceSynchronizationPoint
-------------------------------------------




### Synopsis
Configure an asset intelligence synchronization point.



---


### Description

The Set-CMAssetIntelligenceSynchronizationPoint cmdlet configures an asset intelligence synchronization point. Enable the asset intelligence synchronization point to schedule catalog synchronization with the Microsoft cloud.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMAssetIntelligenceSynchronizationPoint](Add-CMAssetIntelligenceSynchronizationPoint)



* [Get-CMAssetIntelligenceSynchronizationPoint](Get-CMAssetIntelligenceSynchronizationPoint)



* [Remove-CMAssetIntelligenceSynchronizationPoint](Remove-CMAssetIntelligenceSynchronizationPoint)





---


### Examples
#### Example 1: Enable an asset intelligence synchronization point
```PowerShell
$aisp = Get-CMAssetIntelligenceSynchronizationPoint -SiteSystemServerName "CMDIV-WEST04.CORP.CONTOSO.COM"

Set-CMAssetIntelligenceSynchronizationPoint -InputObject $aisp -Enable $True
```



---


### Parameters
#### **CertificateFile**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Enable**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSynchronization**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies an asset intelligence synchronization point object. To get a asset intelligence synchronization point object, use the Get-CMAssetIntelligenceSynchronizationPoint (Get-CMAssetIntelligenceSynchronizationPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                            |
|-----------------|--------|--------|--------------|-----------------------------------|
|`[IResultObject]`|false   |named   |True (ByValue)|AssetIntelligenceUpdateServicePoint|



#### **PassThru**

Returns the current working object. By default, this cmdlet doesn't generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Schedule**

Specifies a CMSchedule object. The schedule specifies when the synchronization occurs. To create a CMSchedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases      |
|-----------------|--------|--------|-------------|-------------|
|`[IResultObject]`|false   |named   |False        |ScheduleToken|



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
Set-CMAssetIntelligenceSynchronizationPoint [-CertificateFile <String>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableSynchronization <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
