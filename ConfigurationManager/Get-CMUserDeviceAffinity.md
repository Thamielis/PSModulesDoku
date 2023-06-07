Get-CMUserDeviceAffinity
------------------------




### Synopsis
Get the relationships between a device and its primary users.



---


### Description

The Get-CMUserDeviceAffinity cmdlet gets one or more user device affinities in Configuration Manager. User device affinities are the relationships between a device and its primary users. For more information, see Link users and devices with user device affinity in Configuration Manager (/mem/configmgr/apps/deploy-use/link-users-and-devices-with-user-device-affinity).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMUserDeviceAffinityRequest](Approve-CMUserDeviceAffinityRequest)



* [Deny-CMUserDeviceAffinityRequest](Deny-CMUserDeviceAffinityRequest)



* [Get-CMUserDeviceAffinityRequest](Get-CMUserDeviceAffinityRequest)



* [Import-CMUserDeviceAffinity](Import-CMUserDeviceAffinity)



* [Link users and devices with user device affinity in Configuration Manager](Link users and devices with user device affinity in Configuration Manager)





---


### Examples
#### Example 1: Get user device affinities by user name
```PowerShell
Get-CMUserDeviceAffinity -UserName "contoso\jqpublic"
```

#### Example 2: Get devices for a given user
```PowerShell
PS XYZ:\> $user = "contoso\jqpublic"
PS XYZ:\> Get-CMUserDeviceAffinity -UserName $user | Select-Object ResourceName
ResourceName
------------
PUYALLUP01
KULSHAN02
TAHOMA42
```

#### Example 3: Get user device affinities by user ID
```PowerShell
Get-CMUserDeviceAffinity -UserID "2063597981"
```

#### Example 4: Get a user device affinity for a device name
```PowerShell
Get-CMUserDeviceAffinity -DeviceName "CMCEN-DIST02"
```

#### Example 5: Get a user device affinity for a device ID
```PowerShell
Get-CMUserDeviceAffinity -DeviceID "16780642"
```

#### Example 6: Get primary users for a list of devices
```PowerShell
$computers = Import-Csv -Path "C:\Users\jqpublic\computers.csv"

foreach ( $computer in $computers )
{
  $uda = Get-CMUserDeviceAffinity -DeviceName $computer.Name
  
  if ( ($uda.UniqueUserName).count -gt 1 )
  {
    foreach ( $user in $uda.UniqueUserName )
    {
      Write-Host $uda.ResourceName[1] $user
    }
  }
  else
  {
    write-host $uda.ResourceName $uda.UniqueUserName
  }
}
```
The script sample uses the Import-Csv cmdlet to take input from a comma-separated list that has a Name column for the device name.


- The first `foreach` command loops through each line from the comma-separated file. It uses the Get-CMUserDeviceAffinity cmdlet to get the primary users for that device. - If there are more than one primary users of the device, then it writes the computer name and each user on a separate line.


- If there is only one primary user of the device, it writes the computer name and the user.


- The output of the script is a simple list of computer names and associated primary user names.


---


### Parameters
#### **DeviceId**

Specify an array of device resource IDs to get their primary users.






|Type       |Required|Position|PipelineInput|Aliases   |
|-----------|--------|--------|-------------|----------|
|`[Int32[]]`|true    |named   |False        |ResourceId|



#### **DeviceName**

Specify an array of device names.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|true    |named   |False        |ResourceName|



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



#### **ShowApprovedOnly**

Add this parameter to filter out non-approved affinities.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UserId**

Specifies an array of user resource IDs. Use this parameter to get any devices for which this user is the primary user.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Int32[]]`|true    |named   |False        |



#### **UserName**

Specify an array of user names. Use this parameter to get any devices for which this user is the primary user.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|true    |named   |False        |UniqueUserName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_UserMachineRelationship


* IResultObject#SMS_UserMachineRelationship






---


### Notes
For more information on this return object and its properties, see SMS_UserMachineRelationship server WMI class (/mem/configmgr/develop/reference/core/clients/manage/sms_usermachinerelationship-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMUserDeviceAffinity -DeviceId <Int32[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ShowApprovedOnly] [<CommonParameters>]
```
```PowerShell
Get-CMUserDeviceAffinity -DeviceName <String[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ShowApprovedOnly] [<CommonParameters>]
```
```PowerShell
Get-CMUserDeviceAffinity [-DisableWildcardHandling] [-ForceWildcardHandling] [-ShowApprovedOnly] -UserId <Int32[]> [<CommonParameters>]
```
```PowerShell
Get-CMUserDeviceAffinity [-DisableWildcardHandling] [-ForceWildcardHandling] [-ShowApprovedOnly] -UserName <String[]> [<CommonParameters>]
```
