Get-CMDistributionStatus
------------------------




### Synopsis
Get the content status of an object.



---


### Description

Use this cmdlet to get the content status of an object. For example, a package, an application, or a boot image. The results of this command are the same as what displays in the Configuration Manager console in the Content Status area of the Summary tab of the details pane. For more information, see Monitor content you distribute with Configuration Manager (/mem/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed#content-status-monitoring).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Monitor content you distribute with Configuration Manager](Monitor content you distribute with Configuration Manager)





---


### Examples
#### Example 1: Get status for an application using its package ID
```PowerShell
$PackageId = (Get-CMApplication -Name 'WebView2 Redist (x86)').PackageID
Get-CMDistributionStatus -Id $PackageId

SmsProviderObjectPath : SMS_ObjectContentExtraInfo.ObjectID="ScopeId_0D7D8B60-F2F9-484A-B9F3-4A8B68D14D59/Application_8
                        8fe14d8-73b2-43bc-897e-08232861c864"
DateCreated           : 11/5/2020 12:59:19
Description           : Installs the WebView2 cab redist to the console.
FeatureType           : 8
LastUpdateDate        : 2/24/2021 00:02:47
NumberErrors          : 0
NumberInProgress      : 0
NumberSuccess         : 3
NumberUnknown         : 0
ObjectID              : ScopeId_0D7D8B60-F2F9-484A-B9F3-4A8B68D14D59/Application_88fe14d8-73b2-43bc-897e-08232861c864
ObjectType            : 512
ObjectTypeID          : 31
PackageID             : XYZ00810
SoftwareName          : WebView2 Redist (x86)
SourceSite            : XYZ
SourceSize            : 123389
SourceVersion         : 1
Targeted              : 3
```
You can see from this output that the application was distributed to three distribution points, because the Targeted property is `3`. You can also see that the site successfully distributed the content, because the NumberSuccess property is also `3`. For more information about these properties, see SMS_ObjectContentExtraInfo server WMI class (/mem/configmgr/develop/reference/core/servers/console/sms_objectcontentextrainfo-server-wmi-class).


---


### Parameters
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



#### **Id**

Specify the package ID for the object to get its content status. This value is a standard package ID, for example, `XYZ0005E2`.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|false   |named   |False        |PackageId|



#### **InputObject**

Specify an object to get its content status. To get this object, use one of the following cmdlets:


* Get-CMApplication (Get-CMApplication.md)- Get-CMBootImage (Get-CMBootImage.md)- Get-CMDriverPackage (Get-CMDriverPackage.md)- Get-CMOperatingSystemInstaller (Get-CMOperatingSystemInstaller.md) (OS upgrade package)- Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)- Get-CMPackage (Get-CMPackage.md)- Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)- Get-CMSoftwareUpdateDeploymentPackage (Get-CMSoftwareUpdateDeploymentPackage.md)






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_ObjectContentExtraInfo, IResultObject#SMS_ObjectContentExtraInfo






---


### Notes
For more information on this return object and its properties, see SMS_ObjectContentExtraInfo server WMI class (/mem/configmgr/develop/reference/core/servers/console/sms_objectcontentextrainfo-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMDistributionStatus [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDistributionStatus [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
