Set-CMMacDeploymentType
-----------------------




### Synopsis
Sets a Mac deployment type.



---


### Description

The Set-CMMacDeploymentType cmdlet changes the settings for a Mac deployment type.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMMacDeploymentType](Add-CMMacDeploymentType)



* [Get-CMApplication](Get-CMApplication)



* [Get-CMDeploymentType](Get-CMDeploymentType)





---


### Examples
#### Example 1: Rename a deployment type and add a description
```PowerShell
PS XYZ:\> Set-CMMacDeploymentType -ApplicationName "testMac" -DeploymentTypeName "DTMac_updated" -NewName "DTMac" -ContentLocation "\\Server01\Resources\Applications\Mac\Bean.app\Bean.app.cmmac" -PassThru -Comment "test-set-CMMacDeploymentType"
```
This command changes the name of the deployment type named DTMac_Updated for the application named testMac to DTMac, and adds a description. The PassThru parameter indicates that an object will be returned from this command.
#### Example 2: Rename a deployment type and add a description by using the pipeline
```PowerShell
PS XYZ:\> Get-CMDeploymentType -ApplicationName "testMac" -DeploymentTypeName "DTMac" | Set-CMMacDeploymentType -NewName "DTMac_updated" -ContentLocation "\\Server01\Resources\Applications\Mac\Skype.app\Skype.app.cmmac" -PassThru -Comment "test-set-CMMacDeploymentType"
```
This command gets the deployment type object named DTMac for the application named testMac and uses the pipeline operator to pass the object to Set-CMMacDeploymentType . Set-CMMacDeploymentType changes the name of the deployment type to DTMac_updated and adds a description. The PassThru parameter indicates that an object will be returned from this command.


---


### Parameters
#### **AddDetectionClause**

Specifies an array of detection method clauses that this deployment type supports.






|Type                 |Required|Position|PipelineInput|Aliases            |
|---------------------|--------|--------|-------------|-------------------|
|`[DetectionClause[]]`|false   |named   |False        |AddDetectionClauses|



#### **AddLanguage**

Adds an array of languages that this deployment type supports. Provide the languages in the "languagecode2-country" or "languagecode2" format, for example: en, en-US, ja-JP, zh-CN.


For more information, see CultureInfo.Name (/dotnet/api/system.globalization.cultureinfo.name#System_Globalization_CultureInfo_Name).






|Type        |Required|Position|PipelineInput|Aliases                                |
|------------|--------|--------|-------------|---------------------------------------|
|`[String[]]`|false   |named   |False        |AddLanguages<br/>Languages<br/>Language|



#### **AddRequirement**

Adds an array of requirements for this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Rule[]]`|false   |named   |False        |



#### **Application**

Specifies an application object that is associated with this deployment type. To obtain an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **ApplicationId**

Specifies the ID of the application that is associated with this deployment type.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CI_ID<br/>CIId|



#### **ApplicationName**

Specifies the name of the application that is associated with this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Comment**

Specifies a description for this deployment type.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |AdministratorComment|



#### **ContentLocation**

Specifies the path of the content. The site system server requires permissions to read the content files.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentTypeName**

Specifies a display name for this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DetectionClauseConnector**

{{ Fill DetectionClauseConnector Description }}






|Type           |Required|Position|PipelineInput|Aliases                  |
|---------------|--------|--------|-------------|-------------------------|
|`[Hashtable[]]`|false   |named   |False        |DetectionClauseConnectors|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[Switch]`|false   |named   |False        |ForceForUnknownPublisher|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GroupDetectionClauses**

{{ Fill GroupDetectionClauses Description }}






|Type        |Required|Position|PipelineInput|Aliases                           |
|------------|--------|--------|-------------|----------------------------------|
|`[String[]]`|false   |named   |False        |GroupDetectionClausesByLogicalName|



#### **InputObject**

Specifies a Mac deployment type object. To obtain a deployment type object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



#### **NewName**

Specifies a new name for this deployment type.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|false   |named   |False        |NewDeploymentTypeName|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveDetectionClause**








|Type        |Required|Position|PipelineInput|Aliases               |
|------------|--------|--------|-------------|----------------------|
|`[String[]]`|false   |named   |False        |RemoveDetectionClauses|



#### **RemoveLanguage**

Removes an array of existing languages from this deployment type. Provide the languages in the "languagecode2-country" or "languagecode2" format, for example: en, en-US, ja-JP, zh-CN.






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|false   |named   |False        |RemoveLanguages|



#### **RemoveRequirement**

Removes the existing installation requirements from this deployment type.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Rule[]]`|false   |named   |False        |RemoveRequirements|



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
Set-CMMacDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -Application <IResultObject> [-Comment <String>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] [-NewName <String>] [-PassThru] [-RemoveDetectionClause <String[]>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMacDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationId <Int32> [-Comment <String>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] [-NewName <String>] [-PassThru] [-RemoveDetectionClause <String[]>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMacDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationName <String> [-Comment <String>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] [-NewName <String>] [-PassThru] [-RemoveDetectionClause <String[]>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMacDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] [-Comment <String>] [-ContentLocation <String>] [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-RemoveDetectionClause <String[]>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
