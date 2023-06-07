Get-CMApplication
-----------------




### Synopsis
Get an application.



---


### Description

Use this cmdlet to get a Configuration Manager application. A Configuration Manager application defines the metadata about app. An application has one or more deployment types. These deployment types include the installation files and information that are required to install software on devices. A deployment type also has rules, such as detection methods and requirements. These rules specify when and how the client installs the software.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Convert-CMApplication](Convert-CMApplication)



* [ConvertFrom-CMApplication](ConvertFrom-CMApplication)



* [ConvertTo-CMApplication](ConvertTo-CMApplication)



* [Export-CMApplication](Export-CMApplication)



* [Import-CMApplication](Import-CMApplication)



* [New-CMApplication](New-CMApplication)



* [Remove-CMApplication](Remove-CMApplication)



* [Resume-CMApplication](Resume-CMApplication)



* [Set-CMApplication](Set-CMApplication)



* [Suspend-CMApplication](Suspend-CMApplication)





---


### Examples
#### Example 1: Get an application by name
```PowerShell
Get-CMApplication -Name "Application1"
```

#### Example 2: Get the application for a deployment type
```PowerShell
$DeploymentType = Get-CMDeploymentType -DeploymentTypeName "DT2" -ApplicationName "Application1"
$DeploymentType | Get-CMApplication
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the CI_ID of an application to get. For example, `136846`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify a deployment type object to get the associated application. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



#### **ModelName**

Specify the ModelID of an application to get. For example, `136846`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Name**

Specify the name of an application to get.






|Type      |Required|Position|PipelineInput|Aliases                                 |
|----------|--------|--------|-------------|----------------------------------------|
|`[String]`|false   |0       |False        |LocalizedDisplayName<br/>ApplicationName|



#### **ShowHidden**

Add this parameter to show hidden applications. A hidden application has the IsHidden property set to `$true`. A hidden app doesn't display in the Configuration Manager console, and it only returns with this cmdlet when you specify this parameter.


To hide an application, use the following commands:






$app = Get-CMApplication -Name "test app" $app.IsHidden = $true $app.Put()







|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_ApplicationLatest


* IResultObject#SMS_ApplicationLatest


* IResultObject#SMS_Application






---


### Notes
For more information on these return object and their properties, see the following articles:

- SMS_Application server WMI class (/mem/configmgr/develop/reference/apps/sms_application-server-wmi-class)- SMS_ApplicationLatest server WMI class (/mem/configmgr/develop/reference/apps/sms_applicationlatest-server-wmi-class)



---


### Syntax
```PowerShell
Get-CMApplication [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -Id <Int32> [-ShowHidden] [<CommonParameters>]
```
```PowerShell
Get-CMApplication [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -InputObject <IResultObject> [-ShowHidden] [<CommonParameters>]
```
```PowerShell
Get-CMApplication [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -ModelName <String> [-ShowHidden] [<CommonParameters>]
```
```PowerShell
Get-CMApplication [[-Name] <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-ShowHidden] [<CommonParameters>]
```
