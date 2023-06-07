Set-CMApplicationSupersedence
-----------------------------




### Synopsis
Set deployment type supersedence for an application.



---


### Description

Use this cmdlet to set deployment type supersedence for the specified application.



For more information, see Supersede applications (/mem/configmgr/apps/deploy-use/revise-and-supersede-applications#supersedence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplication](Get-CMApplication)



* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Supersede applications](Supersede applications)





---


### Examples
#### Example 1: Add deployment type supersedence
```PowerShell
$AppSupersededName = "Superseded app"
$AppSuperseded = New-CMApplication -Name $AppSupersededName
$OriginalDT = Add-CMScriptDeploymentType -ApplicationName $AppSuperseded -DeploymentTypeName "ScriptDT01" -InstallCommand 'appsetup.exe'

$AppSupersedingName = "Superseding app"
$AppSuperseding = New-CMApplication -Name $AppSupersedingName
$AppSupersedingDT = Add-CMScriptDeploymentType -ApplicationName $AppSuperseding -DeploymentTypeName "ScriptDT02" -InstallCommand 'appsetup2.exe'

Set-CMApplicationSupersedence -ApplicationId ($AppSuperseding.CI_ID) -CurrentDeploymentTypeId ($AppSupersedingDT.CI_ID) -SupersededApplicationId ($AppSuperseded.CI_ID) -OldDeploymentTypeId ($OriginalDT.CI_ID)
```

#### Example 2: Remove deployment type supersedence
```PowerShell
Set-CMApplicationSupersedence -ApplicationName $AppSupersedingName -CurrentDeploymentTypeName ($AppSupersedingDT.LocalizedDisplayName) -SupersededApplicationName $AppSupersededName -OldDeploymentTypeName ($OriginalDT.LocalizedDisplayName) -RemoveSupersedence -Force
```



---


### Parameters
#### **CurrentDeploymentType**

Specify a deployment type object from the superseding application. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                                                |
|-----------------|--------|--------|-------------|-------------------------------------------------------|
|`[IResultObject]`|false   |named   |False        |ReplacementDeploymentType<br/>SupersedingDeploymentType|



#### **CurrentDeploymentTypeId**

Specify the ID of a deployment type from the superseding application.






|Type     |Required|Position|PipelineInput|Aliases                                                                                                                                                                                                                                                           |
|---------|--------|--------|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|`[Int32]`|false   |named   |False        |CurrentDeploymentTypeCIId<br/>CurrentDeploymentTypeCI_ID<br/>ReplacementDeploymentTypeId<br/>ReplacementDeploymentTypeCIId<br/>ReplacementDeploymentTypeCI_ID<br/>SupersedingDeploymentTypeId<br/>SupersedingDeploymentTypeCIId<br/>SupersedingDeploymentTypeCI_ID|



#### **CurrentDeploymentTypeName**

Specify the name of a deployment type from the superseding application.






|Type      |Required|Position|PipelineInput|Aliases                                                        |
|----------|--------|--------|-------------|---------------------------------------------------------------|
|`[String]`|false   |named   |False        |ReplacementDeploymentTypeName<br/>SupersedingDeploymentTypeName|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Add this parameter to run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the current ( superseding ) application.






|Type     |Required|Position|PipelineInput|Aliases                                                                                      |
|---------|--------|--------|-------------|---------------------------------------------------------------------------------------------|
|`[Int32]`|true    |0       |False        |ApplicationId<br/>CurrentApplicationId<br/>CurrentApplicationCIId<br/>CurrentApplicationCI_ID|



#### **InputObject**

Specify an object for the current ( superseding ) application. To get this object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                           |
|-----------------|--------|--------|--------------|----------------------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|Application<br/>CurrentApplication|



#### **IsUninstall**

Set this parameter to `$true` to uninstall the superseded application before the client installs the superseding application.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify the localized display name of the current ( superseding ) application.






|Type      |Required|Position|PipelineInput|Aliases                                                                                                       |
|----------|--------|--------|-------------|--------------------------------------------------------------------------------------------------------------|
|`[String]`|true    |0       |False        |ApplicationName<br/>LocalizedDisplayName<br/>CurrentApplicationName<br/>CurrentApplicationLocalizedDisplayName|



#### **OldDeploymentType**

Specify a deployment type object from the superseded application. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                 |
|-----------------|--------|--------|-------------|------------------------|
|`[IResultObject]`|false   |named   |False        |SupersededDeploymentType|



#### **OldDeploymentTypeId**

Specify the ID of a deployment type from the superseded application.






|Type     |Required|Position|PipelineInput|Aliases                                                                                                                                           |
|---------|--------|--------|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|`[Int32]`|false   |named   |False        |OldDeploymentTypeCIId<br/>OldDeploymentTypeCI_ID<br/>SupersededDeploymentTypeId<br/>SupersededDeploymentTypeCIId<br/>SupersededDeploymentTypeCI_ID|



#### **OldDeploymentTypeName**

Specify the name of a deployment type from the superseded application.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|false   |named   |False        |SupersededDeploymentTypeName|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveSupersedence**

Add this parameter to remove the supersedence relationship.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SupersededApplication**

Specify an object for the old ( superseded ) application. To get this object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **SupersededApplicationId**

Specify the ID of the old ( superseded ) application.






|Type     |Required|Position|PipelineInput|Aliases                                                 |
|---------|--------|--------|-------------|--------------------------------------------------------|
|`[Int32]`|false   |named   |False        |SupersededApplicationCIId<br/>SupersededApplicationCI_ID|



#### **SupersededApplicationName**

Specify the localized display name of the old ( superseded ) application.






|Type      |Required|Position|PipelineInput|Aliases                                  |
|----------|--------|--------|-------------|-----------------------------------------|
|`[String]`|false   |named   |False        |SupersededApplicationLocalizedDisplayName|



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
Set-CMApplicationSupersedence [-Id] <Int32> [-CurrentDeploymentType <IResultObject>] [-CurrentDeploymentTypeId <Int32>] [-CurrentDeploymentTypeName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-IsUninstall <Boolean>] [-OldDeploymentType <IResultObject>] [-OldDeploymentTypeId <Int32>] [-OldDeploymentTypeName <String>] [-PassThru] [-RemoveSupersedence] [-SupersededApplication <IResultObject>] [-SupersededApplicationId <Int32>] [-SupersededApplicationName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationSupersedence [-InputObject] <IResultObject> [-CurrentDeploymentType <IResultObject>] [-CurrentDeploymentTypeId <Int32>] [-CurrentDeploymentTypeName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-IsUninstall <Boolean>] [-OldDeploymentType <IResultObject>] [-OldDeploymentTypeId <Int32>] [-OldDeploymentTypeName <String>] [-PassThru] [-RemoveSupersedence] [-SupersededApplication <IResultObject>] [-SupersededApplicationId <Int32>] [-SupersededApplicationName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationSupersedence [-Name] <String> [-CurrentDeploymentType <IResultObject>] [-CurrentDeploymentTypeId <Int32>] [-CurrentDeploymentTypeName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-IsUninstall <Boolean>] [-OldDeploymentType <IResultObject>] [-OldDeploymentTypeId <Int32>] [-OldDeploymentTypeName <String>] [-PassThru] [-RemoveSupersedence] [-SupersededApplication <IResultObject>] [-SupersededApplicationId <Int32>] [-SupersededApplicationName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
