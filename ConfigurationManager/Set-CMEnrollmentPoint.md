Set-CMEnrollmentPoint
---------------------




### Synopsis
Sets an enrollment point in Configuration Manager.



---


### Description

The Set-CMEnrollmentPoint cmdlet sets an enrollment point in Configuration Manager. An enrollment point is a site system role that uses public key infrastructure (PKI) certificates to complete mobile device enrollment and to provision Intel AMT-based computers.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMEnrollmentPoint](Add-CMEnrollmentPoint)



* [Get-CMEnrollmentPoint](Get-CMEnrollmentPoint)



* [Remove-CMEnrollmentPoint](Remove-CMEnrollmentPoint)





---


### Examples
#### Example 1: Set an enrollment point
```PowerShell
PS XYZ:\> Set-CMEnrollmentPoint -SiteSystemServerName "CM-Contoso.Contoso.Com" -SiteCode "CM2" -UserName "Contoso\ElisaDaugherty"
```
The command sets an enrollment point, and specifies an account name to use to connect to the Configuration Manager database.
#### Example 2: Set an enrollment point with the computer account
```PowerShell
PS XYZ:\> Set-CMEnrollmentPoint -SiteSystemServerName "CM-Contoso.Contoso.Com" -SiteCode "CM2" -UseComputerAccount
```
The command sets an enrollment point by specifying the site system server and site code, and uses the computer account to connect to the Configuration Manager database.
#### Example 3: Set an enrollment point by using an input object
```PowerShell
PS XYZ:\> $Ep = Get-CMEnrollmentPoint -SiteSystemServerName "CM-Contoso.Contoso.Com" -SiteCode "CM2"
PS XYZ:\> Set-CMEnrollmentPoint -InputObject $Ep -UserName "Contoso\ElisaDaugherty"
```
The first command uses the Get-CMEnrollmentPoint cmdlet to get an enrollment point, and stores the result in the $Ep variable.


The second command sets an enrollment point for a server by using the input object stored in the $Ep variable.


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

Specifies an input object. To get an input object, use the Get-CMEnrollmentPoint (Get-CMEnrollmentPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |named   |True (ByValue)|EnrollmentPoint|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the fully qualified domain name (FQDN) of the server that hosts the site system role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **UseComputerAccount**

Indicates that you use the computer account to connect to the Configuration Manager database.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UserName**

Specifies a user account that the enrollment point uses to connect to the Configuration Manager database.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Set-CMEnrollmentPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-UseComputerAccount] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMEnrollmentPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-SiteCode <String>] [-UseComputerAccount] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
