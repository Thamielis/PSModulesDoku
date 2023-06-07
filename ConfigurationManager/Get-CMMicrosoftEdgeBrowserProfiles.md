Get-CMMicrosoftEdgeBrowserProfiles
----------------------------------




### Synopsis
Get a policy for a Microsoft Edge Legacy browser profile.



---


### Description

Get a policy for a Microsoft Edge Legacy browser profile. This policy only applies to clients on Windows 10, version 1703 or later, and Microsoft Edge Legacy version 45 and earlier. For more information, see Configure Microsoft Edge Legacy settings in Configuration Manager (/mem/configmgr/compliance/deploy-use/browser-profiles).



For more information on managing Microsoft Edge version 77 or later with Configuration Manager, see Deploy Microsoft Edge, version 77 and later (/mem/configmgr/apps/deploy-use/deploy-edge). For more information on configuring policies for Microsoft Edge version 77 or later, see [Microsoft Edge - Policies](/DeployEdge/microsoft-edge-policies).



---


### Related Links
* [New-CMMicrosoftEdgeBrowserProfiles](New-CMMicrosoftEdgeBrowserProfiles)



* [Set-CMMicrosoftEdgeBrowserProfiles](Set-CMMicrosoftEdgeBrowserProfiles)



* [Configure Microsoft Edge Legacy settings in Configuration Manager](Configure Microsoft Edge Legacy settings in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Get-CMMicrosoftEdgeBrowserProfiles -Id 88156 -Fast | Select-Object LocalizedDisplayName
```



---


### Parameters
#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the CI ID of the browser profile to get. The format is a five- to seven-digit number, for example `403823`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **Name**

Specify the name of the browser profile to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Get-CMMicrosoftEdgeBrowserProfiles [-Id] <Int32> [-Fast] [<CommonParameters>]
```
```PowerShell
Get-CMMicrosoftEdgeBrowserProfiles [-Name] <String> [-Fast] [<CommonParameters>]
```
