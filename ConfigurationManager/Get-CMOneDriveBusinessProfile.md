Get-CMOneDriveBusinessProfile
-----------------------------




### Synopsis
Get a policy for a OneDrive for Business profile.



---


### Description

Get a policy for a OneDrive for Business profile. For more information, see OneDrive for Business profiles (/mem/configmgr/compliance/deploy-use/onedrive-profile).



---


### Related Links
* [New-CMOneDriveBusinessProfile](New-CMOneDriveBusinessProfile)



* [Set-CMOneDriveBusinessProfile](Set-CMOneDriveBusinessProfile)



* [OneDrive for Business profiles](OneDrive for Business profiles)





---


### Examples
#### Example 1
```PowerShell
Get-CMOneDriveBusinessProfile -Id 584750
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

Specify the CI ID of the OneDrive for Business policy to get. The format is a five- to seven-digit number, for example `403823`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **Name**

Specify the name of the OneDrive for Business policy to get.






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
Get-CMOneDriveBusinessProfile [-Id] <Int32> [-Fast] [<CommonParameters>]
```
```PowerShell
Get-CMOneDriveBusinessProfile [-Name] <String> [-Fast] [<CommonParameters>]
```
