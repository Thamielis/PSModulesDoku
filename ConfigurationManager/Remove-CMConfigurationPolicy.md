Remove-CMConfigurationPolicy
----------------------------




### Synopsis
Removes a configuration policy.



---


### Description

The Remove-CMConfigurationPolicy cmdlet removes a configuration policy. A configuration policy can be an email profile, a firewall policy, or others. See the Alias section for additional policy types that you can use this cmdlet to remove.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMConfigurationPolicy](Copy-CMConfigurationPolicy)



* [Get-CMConfigurationPolicy](Get-CMConfigurationPolicy)





---


### Examples
#### Example 1: Remove a configuration policy by ID
```PowerShell
PS XYZ:\> Remove-CMConfigurationPolicy -ID 16777454 -Force
```
This command removes the configuration policy with the CI_ID of 16777454, without prompting the user for confirmation.
#### Example 2: Remove a configuration policy by name
```PowerShell
PS XYZ:\> Get-CMcertificateProfilePfx -Name "CertProf1" | Remove-CMConfigurationPolicy
```
This command gets the PFX certificate profile object named CertProf01 and uses the pipeline operator to pass the object to Remove-CMConfigurationPolicy which removes the certificate profile.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the CI__ID of a configuration policy.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a configuration policy object. To obtain a configuration policy object, use the Get-CMConfigurationPolicy cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies an array of names of configuration policies.






|Type        |Required|Position|PipelineInput|Aliases             |
|------------|--------|--------|-------------|--------------------|
|`[String[]]`|true    |0       |False        |LocalizedDisplayName|



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
Remove-CMConfigurationPolicy [-Id] <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMConfigurationPolicy [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMConfigurationPolicy [-Name] <String[]> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
