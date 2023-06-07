Get-CMObjectLockDetails
-----------------------




### Synopsis
Get the details of a SEDO lock for an object.



---


### Description

Use this cmdlet to get the SEDO lock details for an object. Configuration Manager SEDO (Serialized Editing of Distributed Objects) is a mechanism to assign locks to globally replicated objects. If a user wants to edit and save an object, they have to get a lock from the site. The site assigns a lock to the user for that object, on their computer, and in the site. While the user has the lock, no one else can edit the object.



For more information, see Configuration Manager SEDO (/mem/configmgr/develop/core/understand/sedo).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Lock-CMObject](Lock-CMObject)



* [Unlock-CMObject](Unlock-CMObject)



* [Configuration Manager SEDO](Configuration Manager SEDO)





---


### Examples
#### Example 1: Get object lock details for an application
```PowerShell
PS XYZ:\> Get-CMApplication -Name "Central app" | Get-CMObjectLockDetails


SmsProviderObjectPath     : __PARAMETERS
AssignedMachine           : DESKTOP-VKJQV9N
AssignedObjectLockContext : 36b0ab13-ebe3-4977-8aab-19a701b1c1b6
AssignedSiteCode          : XYZ
AssignedTimeUTC           : 1/5/2021 08:08:39
AssignedUser              : CONTOSO\jqpublic
LockState                 : 1
ReturnValue               : 0
```
When there's no lock on the object, the output is similar but many of the properties are blank. The values aren't `$null`, but an empty string `""`.
#### Example 2: Check for a lock before editing an object
```PowerShell
$app617 = Get-CMApplication -ApplicationName "LOB app v6.17"
$lockUser = ($app617 | Get-CMObjectLockDetails).AssignedUser

if ( $lockUser -eq "" ) {
  Set-CMApplication -InputObject $app617 -NewName "Central app v6.17"
} else {
  Write-Warning "There's a SEDO lock on app $($app617.LocalizedDisplayName)"
}
```



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



#### **InputObject**

Specify a Configuration Manager object that's output from another cmdlet. For example, to get an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.


For a list of objects that are SEDO-enabled, see Configuration Manager SEDO (/mem/configmgr/develop/core/understand/sedo).






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|





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
Get-CMObjectLockDetails [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
