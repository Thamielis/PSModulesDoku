Set-CMClientPushInstallation
----------------------------




### Synopsis
Configure settings for client push installation.



---


### Description

Use this cmdlet to change the site configuration for client push installation. The client push installation method installs the Configuration Manager client on computers that the site discovers.



You can also start a client push installation by running the Client Push Installation Wizard for a specific collection or resource within a collection.



For more information, see How to install clients on Windows-based computers in Configuration Manager (/mem/configmgr/core/clients/deploy/deploy-clients-to-windows-computers#BKMK_ClientPush).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMClientPushInstallation](Get-CMClientPushInstallation)



* [How to install clients on Windows-based computers in Configuration Manager](How to install clients on Windows-based computers in Configuration Manager)





---


### Examples
#### Example 1: Change the settings of a client push installation
```PowerShell
Set-CMClientPushInstallation -SiteCode "CM1" -EnableAutomaticClientPushInstallation $True -EnableSystemTypeConfiguationManager $True -ChosenAccount "contoso\svc_smspush" -InstallationProperty "SMSSITECODE=CM1"
```



---


### Parameters
#### **AddAccount**

Specify a string array for one or more accounts that can install the client. The accounts need to be a local Administrator on the destination computer. For each account, use the format `domain\username`.


For more information, see Client push installation account (/mem/configmgr/core/plan-design/hierarchy/accounts#client-push-installation-account).






|Type        |Required|Position|PipelineInput|Aliases    |
|------------|--------|--------|-------------|-----------|
|`[String[]]`|false   |named   |False        |AddAccounts|



#### **AllownNTLMFallback**

When this parameter is $true , if the site can't authenticate the client by using Kerberos, it retries the connection by using NTLM. The recommended configuration for improved security is to set this parameter to $false , which requires Kerberos without NTLM fallback.


> [!NOTE] > When it uses client push to install the Configuration Manager client, the site server creates a remote connection to the client. The site can require Kerberos mutual authentication by not allowing fallback to NTLM before establishing the connection. This behavior helps to secure the communication between the server and the client. > > Depending on your security policies, your environment might already prefer or require Kerberos over the older NTLM authentication. For more information on the security considerations of these authentication protocols, read about the Windows security policy setting to restrict NTLM (/windows/security/threat-protection/security-policy-settings/network-security-restrict-ntlm-outgoing-ntlm-traffic-to-remote-servers#security-considerations). > > To use this feature, clients must be in a trusted Active Directory forest. Kerberos in Windows relies on Active Directory for mutual authentication.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ChosenAccount**

Specify a string array for one or more accounts already added to Configuration Manager.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|false   |named   |False        |ChosenAccounts|



#### **ClearAccount**

Add this parameter to remove all accounts that are currently specified for client push at the site. To remove a single account, use the RemoveAccount parameter.






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[Switch]`|false   |named   |False        |ClearAccounts|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableAutomaticClientPushInstallation**

Set this parameter to $true to install the Configuration Manager client on newly discovered computer resources. It also enables installation on existing computer resources that don't have the client installed.


If you set this parameter to $false , you can still use the Install client (/mem/configmgr/core/clients/manage/client-notification#install-client)action on a collection or device.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSystemTypeConfigurationManager**

Set this parameter to $true to install the Configuration Manager client on site system servers.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSystemTypeServer**

Set this parameter to $true to install the Configuration Manager client on servers.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSystemTypeWorkstation**

Set this parameter to $true to install the Configuration Manager client on workstations.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a client push installation object. To get this object, use the Get-CMClientPushInstallation (Get-CMClientPushInstallation.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ClientPushComponent|



#### **InstallationProperty**

Specify any installation properties to use when installing the Configuration Manager client.


For example:


`/mp:mp01.contoso.com CCMDEBUGLOGGING="1" CCMLOGGINGENABLED="TRUE" CCMLOGLEVEL="0" CCMLOGMAXHISTORY="5" CCMLOGMAXSIZE="10000000" SMSCACHESIZE="15000" SMSSITECODE="XYZ" SMSMP=mp01.contoso.com`


For more information, see About client installation parameters and properties in Configuration Manager (/mem/configmgr/core/clients/deploy/about-client-installation-properties).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InstallClientToDomainController**

Set this parameter to specify whether to install the Configuration Manager client on domain controllers:


* $true : Always install the client on domain controllers. - $false : Never install the client on domain controllers, unless specified in the Client Push Installation Wizard.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specifies a name for the client push installation.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteName|



#### **RemoveAccount**

Specify a string array of client push installation accounts to remove. To remove all accounts, use the ClearAccount parameter.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|false   |named   |False        |RemoveAccounts|



#### **SiteCode**

Specify the three character site code. For example, `XYZ`.






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
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMClientPushInstallation [-AddAccount <String[]>] [-AllownNTLMFallback <Boolean>] [-ChosenAccount <String[]>] [-ClearAccount] [-DisableWildcardHandling] [-EnableAutomaticClientPushInstallation <Boolean>] [-EnableSystemTypeConfigurationManager <Boolean>] [-EnableSystemTypeServer <Boolean>] [-EnableSystemTypeWorkstation <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallationProperty <String>] [-InstallClientToDomainController <Boolean>] [-RemoveAccount <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientPushInstallation [-AddAccount <String[]>] [-AllownNTLMFallback <Boolean>] [-ChosenAccount <String[]>] [-ClearAccount] [-DisableWildcardHandling] [-EnableAutomaticClientPushInstallation <Boolean>] [-EnableSystemTypeConfigurationManager <Boolean>] [-EnableSystemTypeServer <Boolean>] [-EnableSystemTypeWorkstation <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallationProperty <String>] [-InstallClientToDomainController <Boolean>] [-RemoveAccount <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientPushInstallation [-AddAccount <String[]>] [-AllownNTLMFallback <Boolean>] [-ChosenAccount <String[]>] [-ClearAccount] [-DisableWildcardHandling] [-EnableAutomaticClientPushInstallation <Boolean>] [-EnableSystemTypeConfigurationManager <Boolean>] [-EnableSystemTypeServer <Boolean>] [-EnableSystemTypeWorkstation <Boolean>] [-ForceWildcardHandling] [-InstallationProperty <String>] [-InstallClientToDomainController <Boolean>] -Name <String> [-RemoveAccount <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientPushInstallation [-AddAccount <String[]>] [-AllownNTLMFallback <Boolean>] [-ChosenAccount <String[]>] [-ClearAccount] [-DisableWildcardHandling] [-EnableAutomaticClientPushInstallation <Boolean>] [-EnableSystemTypeConfigurationManager <Boolean>] [-EnableSystemTypeServer <Boolean>] [-EnableSystemTypeWorkstation <Boolean>] [-ForceWildcardHandling] [-InstallationProperty <String>] [-InstallClientToDomainController <Boolean>] [-RemoveAccount <String[]>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
