Export-CMApplication
--------------------




### Synopsis
Exports an application.



---


### Description

The Export-CMApplication cmdlet exports an application to a file. Specify a file path to the location where you want to export the application.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [ConvertFrom-CMApplication](ConvertFrom-CMApplication)



* [ConvertTo-CMApplication](ConvertTo-CMApplication)



* [Get-CMApplication](Get-CMApplication)



* [Import-CMApplication](Import-CMApplication)



* [New-CMApplication](New-CMApplication)



* [Remove-CMApplication](Remove-CMApplication)



* [Resume-CMApplication](Resume-CMApplication)



* [Set-CMApplication](Set-CMApplication)



* [Suspend-CMApplication](Suspend-CMApplication)





---


### Examples
#### Example 1: Get an application and export it
```PowerShell
PS XYZ:\> Get-CMApplication "Application01" | Export-CMApplication -Path "C:\test.zip" -IgnoreRelated -OmitContent -Comment "Application export" -Force
```
This command gets the application object named Applicaton01 and uses the pipeline operator to pass the object to Export-CMApplicaton . Export-CMApplication exports the application to the path C:\test.zip, omitting related content from the zip file, and not exporting related objects. Specifying the Force parameter indicates that the application is exported without prompting the user.
#### Example 2: Export an application
```PowerShell
PS XYZ:\>Export-CMApplication -Name "Application01" -Path "C:\test.zip" -IgnoreRelated -OmitContent -Comment "Application export"
```
This command exports the application named Application01 to the path C:\test.zip, omitting related content from the zip file, and not exporting related objects. Specifying the Force parameter indicates that the application is exported without prompting the user.


---


### Parameters
#### **Comment**

Specifies a comment for the exported application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Performs the action without a confirmation message.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the ID of the application to export.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **IgnoreRelated**

Indicates that related objects, such as application dependencies, superseded applications, or related categories and global conditions, are not exported.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies an application object. To obtain an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies the name of the application to export.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **OmitContent**

Indicates that the cmdlet exports related content to a separate folder in the same location as the .zip file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

Specifies a path for the package. The package file has a .zip extension.






|Type      |Required|Position|PipelineInput|Aliases                                 |
|----------|--------|--------|-------------|----------------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>ExportFilePath|



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
Export-CMApplication [-Comment <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <Int32> [-IgnoreRelated] [-OmitContent] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMApplication [-Comment <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-IgnoreRelated] -InputObject <IResultObject> [-OmitContent] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMApplication [-Comment <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-IgnoreRelated] -Name <String> [-OmitContent] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
