Set-CMEmailNotificationComponent
--------------------------------




### Synopsis
Changes configuration settings of an email notification component.



---


### Description

The Set-CMEmailNotificationComponent cmdlet changes configuration settings of an email notification component in Configuration Manager. You can configure the email notification component for each Configuration Manager site to configure email subscriptions to alerts.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMEmailNotificationComponent](Get-CMEmailNotificationComponent)





---


### Examples
#### Example 1: Enable email notification
```PowerShell
PS XYZ:\> Set-CMEmailNotificationComponent -SiteSystemServerName "cmcen-dist02.tsqa.corp.contoso.com" -SiteCode "CM2" -EnableEmailNotification $True -MstpServerFqdn "mail.corp.contosco.com" -Port 25 -TypeOfAuthentication DefaultServiceAccount -SendFrom "evan.narvaez@contoso.com"
```
This command enables email notification for Configuration Manager. The command specifies that Configuration Manager uses the Configuration Manager site that has the site code CM2 on the server cmcen-dist02.tsqa.corp.contoso.com to host the site system role for email notification. The command specifies that Configuration Manager uses the server named mail.corp.contosco.com for the email server and specifies the outgoing SMTP port for sending email alerts. The command specifies that Configuration Manager uses the default service account for authenticating the site server to the SMTP Server, and specifies that Configuration Manager sends email alerts from the email address evan.narvaez@contoso.com.
#### Example 2: Disable email notification
```PowerShell
PS XYZ:\> Set-CMEmailNotificationComponent -SiteSystemServerName "cmcen-dist02.tsqa.corp.contoso.com" -EnableEmailNotification $False
```
This command disables email notification for Configuration Manager on the site server named cmcen-dist02.tsqa.corp.contoso.com.
#### Example 3: Set the outgoing SMTP port for email notification
```PowerShell
PS XYZ:\> Set-CMEmailNotificationComponent -SiteSystemServerName "cmcen-dist02.tsqa.corp.contoso.com" -Port 27
```
This command sets the outgoing SMTP port that Configuration Manager uses for sending email alerts on the site server named cmcen-dist02.tsqa.corp.contoso.com to port 27.


---


### Parameters
#### **DisableEmailNotification**

Indicates that email notification is disabled.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |0       |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableEmailNotification**

Indicates that Configuration Manager uses an SMTP server to send email alerts.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |0       |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Port**

Specifies the outgoing SMTP port for sending email alerts.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SendFrom**

Specifies the email address from which Configuration Manager sends email alerts.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SmtpServerFqdn**

Specifies the fully qualified domain name (FQDN) of the SMTP server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TypeOfAuthentication**

Specifies the method by which Configuration Manager authenticates the site server to the SMTP Server. The acceptable values for this parameter are:


* Anonymous


* DefaultServiceAccount


* Other



Valid Values:

* Anonymous
* DefaultServiceAccount
* Other






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[AuthenticationMethod]`|true    |named   |False        |



#### **UserName**

Specifies the user name to authenticate with the SMTP server from which Configuration Manager sends email alerts. This parameter also specifies the SMTP Server Connection account.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UseSsl**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
None





---


### Outputs
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMEmailNotificationComponent [-DisableEmailNotification] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMEmailNotificationComponent [-EnableEmailNotification] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Port <Int32>] -SendFrom <String> -SmtpServerFqdn <String> -TypeOfAuthentication {Anonymous | DefaultServiceAccount | Other} [-UserName <String>] [-UseSsl <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
