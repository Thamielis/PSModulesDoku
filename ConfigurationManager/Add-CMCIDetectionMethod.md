Add-CMCIDetectionMethod
-----------------------




### Synopsis
Specify how the client detects an application.



---


### Description

This cmdlet specifies how the client detects an application on the device. There are three detection methods: Windows Installer detection, detection by a specific application and deployment type, and a custom script to detect the application.



---


### Related Links
* [Get-CMConfigurationItem](Get-CMConfigurationItem)



* [Get-CMDeploymentType](Get-CMDeploymentType)





---


### Examples
#### Example 1: Windows Installer detection
```PowerShell
$ci = Get-CMConfigurationItem -Name "testCI"

$msiFilePath = "C:\tools\CCMTools\Orca.Msi"

$ci | Add-CMCIDetectionMethod -DetectionOption Msi -MsiFilePath $msiFilePath
```

#### Example 2: Specific app and deployment type
```PowerShell
$ci = Get-CMConfigurationItem -Name "testCI"

$ci | Add-CMCIDetectionMethod -DetectionOption DeploymentType -ApplicationName "testApp" -DeploymentTypeId "392672"
```

#### Example 3: Custom script detection
```PowerShell
$ci = Get-CMConfigurationItem -Name "testCI"

$scriptFile  = "C:\share\testScript.ps1"

$ci | Add-CMCIDetectionMethod -DetectionOption Script -ScriptLanguage PowerShell -ScriptFile $scriptFile
```



---


### Parameters
#### **ApplicationName**

When you set the DetectionOption to `DeploymentType`, use this parameter to specify the name of a Configuration Manager application. Use this parameter with DeploymentTypeID .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentTypeId**

When you set the DetectionOption to `DeploymentType`, use this parameter to specify the ID of deployment type of the Configuration Manager application. Use this parameter with ApplicationName .


To get the deployment type ID, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet, and reference the CI_ID property.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DetectionOption**

Specify the method of detection to use.



Valid Values:

* None
* Msi
* Script
* DeploymentType






|Type                          |Required|Position|PipelineInput|
|------------------------------|--------|--------|-------------|
|`[ApplicationDetectionMethod]`|true    |named   |False        |



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

Specify a configuration item object for an application deployment type. To get this object, use Get-CMConfigurationItem (Get-CMConfigurationItem.md).






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **IsPerUserInstallation**

Set this parameter to `$true` to specify that it's installed per user.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MsiFilePath**

When you set DetectionOption to `Msi`, use this parameter to specify the path to the Windows Installer file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ScriptFile**

When you set DetectionOption to `Script`, use this parameter to specify the path to the script. Use this parameter with ScriptLanguage .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ScriptLanguage**

When you set DetectionOption to `Script`, use this parameter to specify the language of the script. Use this parameter with ScriptFile and ScriptText .



Valid Values:

* PowerShell
* VBScript
* JScript
* ShellScript






|Type                 |Required|Position|PipelineInput|Aliases   |
|---------------------|--------|--------|-------------|----------|
|`[ScriptingLanguage]`|false   |named   |False        |ScriptType|



#### **ScriptText**

When you set DetectionOption to `Script`, use this parameter to specify the text of the script. Use this parameter with ScriptLanguage .






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[String]`|false   |named   |False        |ScriptContent|



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
Add-CMCIDetectionMethod [-InputObject] <IResultObject> [-ApplicationName <String>] [-DeploymentTypeId <String>] -DetectionOption {None | Msi | Script | DeploymentType} [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsPerUserInstallation <Boolean>] [-MsiFilePath <String>] [-PassThru] [-ScriptFile <String>] [-ScriptLanguage {PowerShell | VBScript | JScript}] [-ScriptText <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
