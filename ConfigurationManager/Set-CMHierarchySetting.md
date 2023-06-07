Set-CMHierarchySetting
----------------------




### Synopsis
Sets hierarchy settings in Configuration Manager.



---


### Description

The Set-CMHierarchySetting cmdlet sets hierarchy settings in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Modify the hierarchy setting
```PowerShell
PS XYZ:\> Set-CMHierarchySetting -AllowPrestage -ApprovalMethod AutomaticallyApproveAllComputers
```
This command uses the Set-CMHierarchySetting cmdlet to modify the hierarchy setting. The command specifies the value AutomaticallyApproveAllComputers for the ApprovalMethod parameter, and also specifies the AllowPrestage parameter.


---


### Parameters
#### **AllowPrestage**

Indicates whether to allow prestaging.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ApprovalMethod**

Specifies an approval method. Valid values are:


* AutomaticallyApproveAllComputers


* AutomaticallyApproveComputersInTrustedDomains


* ManuallyApproveEachComputer



Valid Values:

* AutomaticallyApproveComputersInTrustedDomains
* ManuallyApproveEachComputer
* AutomaticallyApproveAllComputers






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[ApprovalMethodType]`|false   |named   |False        |



#### **AutoResolveClientConflict**








|Type       |Required|Position|PipelineInput|Aliases                                                                       |
|-----------|--------|--------|-------------|------------------------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |AutomaticallyResolveConfictingRecord<br/>AutomaticallyResolveConflictingRecord|



#### **AutoUpgradeDays**








|Type     |Required|Position|PipelineInput|Aliases                 |
|---------|--------|--------|-------------|------------------------|
|`[Int32]`|false   |named   |False        |AutomaticallyUpgradeDays|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableAutoClientUpgrade**








|Type       |Required|Position|PipelineInput|Aliases      |
|-----------|--------|--------|-------------|-------------|
|`[Boolean]`|false   |named   |False        |EnableProgram|



#### **EnableExclusionCollection**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnablePreProduction**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnablePrereleaseFeature**








|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[Switch]`|false   |named   |False        |EnablePrereleaseFeatures|



#### **ExcludeServer**

Indicates whether the cmdlet excludes the server.






|Type       |Required|Position|PipelineInput|Aliases       |
|-----------|--------|--------|-------------|--------------|
|`[Boolean]`|false   |named   |False        |ExcludeServers|



#### **ExclusionCollection**








|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **ExclusionCollectionId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ExclusionCollectionName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FallbackSiteCode**

Specifies the site code for a fallback site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PreferBoundaryGroupManagementPoint**








|Type       |Required|Position|PipelineInput|Aliases                            |
|-----------|--------|--------|-------------|-----------------------------------|
|`[Boolean]`|false   |named   |False        |PreferBoundaryGroupManagementPoints|



#### **TargetCollection**








|Type             |Required|Position|PipelineInput|Aliases                |
|-----------------|--------|--------|-------------|-----------------------|
|`[IResultObject]`|false   |named   |False        |PreProductionCollection|



#### **TargetCollectionId**








|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|false   |named   |False        |PreProductionCollectionId|



#### **TargetCollectionName**








|Type      |Required|Position|PipelineInput|Aliases                    |
|----------|--------|--------|-------------|---------------------------|
|`[String]`|false   |named   |False        |PreProductionCollectionName|



#### **TelemetryLevel**

{{ Fill TelemetryLevel Description }}



Valid Values:

* Basic
* Enhanced
* Full






|Type                  |Required|Position|PipelineInput|Aliases        |
|----------------------|--------|--------|-------------|---------------|
|`[TelemetryLevelType]`|false   |named   |False        |DiagnosticLevel|



#### **UnlimitTargetCollectionMember**








|Type      |Required|Position|PipelineInput|Aliases                                  |
|----------|--------|--------|-------------|-----------------------------------------|
|`[Switch]`|false   |named   |False        |UnlimitPreProductionCollectionMemberCount|



#### **UseFallbackSite**

Indicates whether to use a fallback site.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* IResultObject#SMS_SCI_SiteDefinition


* IResultObject[]#SMS_SCI_SiteDefinition






---


### Notes




---


### Syntax
```PowerShell
Set-CMHierarchySetting [-AllowPrestage <Boolean>] [-ApprovalMethod {AutomaticallyApproveComputersInTrustedDomains | ManuallyApproveEachComputer | AutomaticallyApproveAllComputers}] [-AutoResolveClientConflict <Boolean>] [-AutoUpgradeDays <Int32>] [-DisableWildcardHandling] [-EnableAutoClientUpgrade <Boolean>] [-EnableExclusionCollection <Boolean>] [-EnablePreProduction <Boolean>] [-EnablePrereleaseFeature] [-ExcludeServer <Boolean>] [-ExclusionCollection <IResultObject>] [-ExclusionCollectionId <String>] [-ExclusionCollectionName <String>] [-FallbackSiteCode <String>] [-Force] [-ForceWildcardHandling] [-PassThru] [-PreferBoundaryGroupManagementPoint <Boolean>] [-TargetCollection <IResultObject>] [-TargetCollectionId <String>] [-TargetCollectionName <String>] [-TelemetryLevel {Basic | Enhanced | Full}] [-UnlimitTargetCollectionMember] [-UseFallbackSite <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
