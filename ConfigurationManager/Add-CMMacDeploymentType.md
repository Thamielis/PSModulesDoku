Add-CMMacDeploymentType
-----------------------




### Synopsis
Adds a Mac deployment type.



---


### Description

The Add-CMMacDeploymentType cmdlet adds a Mac deployment type to an application.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplication](Get-CMApplication)



* [Set-CMMacDeploymentType](Set-CMMacDeploymentType)





---


### Examples
#### Example 1: Add a Mac deployment type
```PowerShell
PS XYZ:\>Add-CMMacDeploymentType -ApplicationName "testMac" -DeploymentTypeName "DTMac" -ContentLocation "\\Server01\Resources\Applications\Mac\Bean.app\Bean.app.cmmac" -Confirm -Comment "create a mac DT" -AddLanguage "en-US","zh-CN"
```
This command adds the Mac deployment type named DTMac from the specified URL to the application named testMac in English and Chinese. By using the Confirm parameter, the user is prompted for confirmation before the cmdlet runs.
#### Example 2: Add a Mac deployment type by using the pipeline
```PowerShell
PS XYZ:\> Get-CMApplication -Name "testMac" | Add-CMMacDeploymentType -DeploymentTypeName "DTMac01" -ContentLocation "\\Server01\Resources\Applications\Mac\Skype.app\Skype.app.cmmac" -WhatIf -Comment "create a mac DT" -AddLanguage "zh-CN"
```
This command gets the application object named testMAC and uses the pipeline operator to pass the object to Add-CMMacDeploymentType . Add-CMMacDeploymentType adds a deployment type named DTMac01 from the specified URL in Chinese. Using the WhatIf parameter returns a description of what would happen if you executed the command but does not actually execute the command.


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

Specifies an array of requirements for the deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Rule[]]`|false   |named   |False        |



#### **ApplicationId**

Specifies the ID of the application that is associated with the deployment type.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CI_ID<br/>CIId|



#### **ApplicationName**

Specifies the name of the application that is associated with the deployment type.






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






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|true    |named   |False        |InstallationFileLocation|



#### **DeploymentTypeName**

Specifies a display name for this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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

Specifies an application object. To obtain an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Application|



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
Add-CMMacDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationId <Int32> [-Comment <String>] -ContentLocation <String> [-DeploymentTypeName <String>] [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMMacDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationName <String> [-Comment <String>] -ContentLocation <String> [-DeploymentTypeName <String>] [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMMacDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] [-Comment <String>] -ContentLocation <String> [-DeploymentTypeName <String>] [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] -InputObject <IResultObject> [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
