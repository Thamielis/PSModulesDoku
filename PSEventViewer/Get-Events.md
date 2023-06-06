Get-Events
----------




### Synopsis
Get-Events is a wrapper function around Get-WinEvent providing additional features and options.



---


### Description

Get-Events is a wrapper function around Get-WinEvent providing additional features and options exposing most of the Get-WinEvent functionality in easy to use manner.



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-Events -LogName 'Application' -ID 1001 -MaxEvents 1 -Verbose -DisableParallel
```

#### EXAMPLE 2
```PowerShell
Get-Events -LogName 'Setup' -ID 2 -ComputerName 'AD1' -MaxEvents 1 -Verbose | Format-List *
```

#### EXAMPLE 3
```PowerShell
Get-Events -LogName 'Setup' -ID 2 -ComputerName 'AD1','AD2','AD3' -MaxEvents 1 -Verbose | Format-List *
```

#### EXAMPLE 4
```PowerShell
Get-Events -LogName 'Security' -ID 5379 -RecordID 19626 -Verbose
```

#### EXAMPLE 5
```PowerShell
Get-Events -LogName 'System' -ID 1001,1018 -ProviderName 'Microsoft-Windows-WER-SystemErrorReporting' -Verbose
Get-Events -LogName 'System' -ID 42,41,109 -ProviderName 'Microsoft-Windows-Kernel-Power' -Verbose
Get-Events -LogName 'System' -ID 1,12,13 -ProviderName 'Microsoft-Windows-Kernel-General' -Verbose
Get-Events -LogName 'System' -ID 6005,6006,6008,6013 -ProviderName 'EventLog' -Verbose
```

#### EXAMPLE 6
```PowerShell
$List = @(
    @{ Server = 'AD1'; LogName = 'Security'; EventID = '5136', '5137'; Type = 'Computer' }
    @{ Server = 'AD2'; LogName = 'Security'; EventID = '5136', '5137'; Type = 'Computer' }
    @{ Server = 'C:\MyEvents\Archive-Security-2018-08-21-23-49-19-424.evtx'; LogName = 'Security'; EventID = '5136', '5137'; Type = 'File' }
    @{ Server = 'C:\MyEvents\Archive-Security-2018-09-15-09-27-52-679.evtx'; LogName = 'Security'; EventID = '5136', '5137'; Type = 'File' }
    @{ Server = 'Evo1'; LogName = 'Setup'; EventID = 2; Type = 'Computer'; }
    @{ Server = 'AD1.ad.evotec.xyz'; LogName = 'Security'; EventID = 4720, 4738, 5136, 5137, 5141, 4722, 4725, 4767, 4723, 4724, 4726, 4728, 4729, 4732, 4733, 4746, 4747, 4751, 4752, 4756, 4757, 4761, 4762, 4785, 4786, 4787, 4788, 5136, 5137, 5141, 5136, 5137, 5141, 5136, 5137, 5141; Type = 'Computer' }
    @{ Server = 'Evo1'; LogName = 'Security'; Type = 'Computer'; MaxEvents = 15; Keywords = 'AuditSuccess' }
    @{ Server = 'Evo1'; LogName = 'Security'; Type = 'Computer'; MaxEvents = 15; Level = 'Informational'; Keywords = 'AuditFailure' }
)
$Output = Get-Events -ExtendedInput $List -Verbose
$Output | Format-Table Computer, Date, LevelDisplayName
```

#### EXAMPLE 7
```PowerShell
Get-Events -MaxEvents 2 -LogName 'Security' -ComputerName 'AD1.AD.EVOTEC.XYZ','AD2' -ID 4720, 4738, 5136, 5137, 5141, 4722, 4725, 4767, 4723, 4724, 4726, 4728, 4729, 4732, 4733, 4746, 4747, 4751, 4752, 4756, 4757, 4761, 4762, 4785, 4786, 4787, 4788, 5136, 5137, 5141, 5136, 5137, 5141, 5136, 5137, 5141 -Verbose
```



---


### Parameters
#### **Machine**

Specifies the name of the computer that this cmdlet gets events from the event logs. Type the NetBIOS name, an IP address, or the fully qualified domain name (FQDN) of the computer. The default value is the local computer, localhost. This parameter accepts only one computer name at a time.

To get event logs from remote computers, configure the firewall port for the event log service to allow remote access.

This cmdlet does not rely on PowerShell remoting. You can use the ComputerName parameter even if your computer is not configured to run remote commands.






|Type        |Required|Position|PipelineInput|Aliases                                                                                                    |
|------------|--------|--------|-------------|-----------------------------------------------------------------------------------------------------------|
|`[String[]]`|false   |1       |false        |ADDomainControllers<br/>DomainController<br/>Server<br/>Servers<br/>Computer<br/>Computers<br/>ComputerName|



#### **DateFrom**

Specifies the date and time of the earliest event in the event log you want to search for.






|Type          |Required|Position|PipelineInput|Aliases           |
|--------------|--------|--------|-------------|------------------|
|`[Nullable`1]`|false   |2       |false        |StartTime<br/>From|



#### **DateTo**

Specifies the date and time of the latest event in the event log you want to search for.






|Type          |Required|Position|PipelineInput|Aliases       |
|--------------|--------|--------|-------------|--------------|
|`[Nullable`1]`|false   |3       |false        |EndTime<br/>To|



#### **ID**

Specifies the event ID (or events) of the event you want to search for. If provided more than 23 the cmdlet will split the events into multiple queries automatically.






|Type       |Required|Position|PipelineInput|Aliases                     |
|-----------|--------|--------|-------------|----------------------------|
|`[Int32[]]`|false   |4       |false        |Ids<br/>EventID<br/>EventIds|



#### **ExcludeID**

Specifies the event ID (or events) of the event you want to exclude from the search. If provided more than 23 the cmdlet will split the events into multiple queries automatically.






|Type       |Required|Position|PipelineInput|Aliases      |
|-----------|--------|--------|-------------|-------------|
|`[Int32[]]`|false   |5       |false        |ExludeEventID|



#### **LogName**

Specifies the event logs that this cmdlet get events from. Enter the event log names in a comma-separated list. Wildcards are permitted.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |6       |false        |LogType<br/>Log|



#### **ProviderName**

Specifies, as a string array, the event log providers from which this cmdlet gets events. Enter the provider names in a comma-separated list, or use wildcard characters to create provider name patterns.

An event log provider is a program or service that writes events to the event log. It is not a PowerShell provider.






|Type        |Required|Position|PipelineInput|Aliases            |
|------------|--------|--------|-------------|-------------------|
|`[String[]]`|false   |7       |false        |Provider<br/>Source|



#### **NamedDataFilter**

Provide NamedDataFilter in specific form to optimize search performance looking for specific events.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |8       |false        |



#### **NamedDataExcludeFilter**

Provide NamedDataExcludeFilter in specific form to optimize search performance looking for specific events.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |9       |false        |



#### **UserID**

The UserID key can take a valid security identifier (SID) or a domain account name that can be used to construct a valid System.Security.Principal.NTAccount object.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |10      |false        |



#### **Level**

Define the event level that this cmdlet gets events from. Options are Verbose, Informational, Warning, Error, Critical, LogAlways



Valid Values:

* LogAlways
* Critical
* Error
* Warning
* Informational
* Verbose






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Level[]]`|false   |11      |false        |



#### **UserSID**

Search events by UserSID






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |12      |false        |



#### **Data**

The Data value takes event data in an unnamed field. For example, events in classic event logs.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |13      |false        |



#### **MaxEvents**

Specifies the maximum number of events that are returned. Enter an integer such as 100. The default is to return all the events in the logs or files.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |14      |false        |



#### **Credential**

Specifies the name of the computer that this cmdlet gets events from the event logs. Type the NetBIOS name, an IP address, or the fully qualified domain name (FQDN) of the computer. The default value is the local computer, localhost. This parameter accepts only one computer name at a time.

To get event logs from remote computers, configure the firewall port for the event log service to allow remote access.

This cmdlet does not rely on PowerShell remoting. You can use the ComputerName parameter even if your computer is not configured to run remote commands.






|Type            |Required|Position|PipelineInput|Aliases    |
|----------------|--------|--------|-------------|-----------|
|`[PSCredential]`|false   |15      |false        |Credentials|



#### **Path**

Specifies the path to the event log files that this cmdlet get events from. Enter the paths to the log files in a comma-separated list, or use wildcard characters to create file path patterns.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |16      |false        |



#### **Keywords**

Define keywords to search for by their name. Available keywords are: AuditFailure, AuditSuccess, CorrelationHint2, EventLogClassic, Sqm, WdiDiagnostic, WdiContext, ResponseTime, None



Valid Values:

* None
* ResponseTime
* WdiContext
* WdiDiagnostic
* Sqm
* AuditFailure
* AuditSuccess
* CorrelationHint2
* EventLogClassic






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[Keywords[]]`|false   |17      |false        |



#### **RecordID**

Find a single event in the event log using it's RecordId






|Type     |Required|Position|PipelineInput|Aliases      |
|---------|--------|--------|-------------|-------------|
|`[Int64]`|false   |18      |false        |EventRecordID|



#### **MaxRunspaces**

Limit the number of concurrent runspaces that can be used to process the events. By default it uses $env:NUMBER_OF_PROCESSORS + 1






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |19      |false        |



#### **Oldest**

Indicate that this cmdlet gets the events in oldest-first order. By default, events are returned in newest-first order.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **DisableParallel**

Disables parallel processing of the events. By default, events are processed in parallel.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **ExtendedOutput**

Indicates that this cmdlet returns an extended set of output parameters. By default, this cmdlet does not generate any extended output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **ExtendedInput**

Indicates that this cmdlet takes an extended set of input parameters. Extended input is used by PSWinReportingV2 to provide special input parameters.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Array]`|false   |20      |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Get-Events [[-Machine] <String[]>] [[-DateFrom] <Nullable`1>] [[-DateTo] <Nullable`1>] [[-ID] <Int32[]>] [[-ExcludeID] <Int32[]>] [[-LogName] <String>] [[-ProviderName] <String[]>] [[-NamedDataFilter] <Hashtable>] [[-NamedDataExcludeFilter] <Hashtable>] [[-UserID] <String[]>] [[-Level] {LogAlways | Critical | Error | Warning | Informational | Verbose}] [[-UserSID] <String>] [[-Data] <String[]>] [[-MaxEvents] <Int32>] [[-Credential] <PSCredential>] [[-Path] <String>] [[-Keywords] {None | ResponseTime | WdiContext | WdiDiagnostic | Sqm | AuditFailure | AuditSuccess | CorrelationHint2 | EventLogClassic}] [[-RecordID] <Int64>] [[-MaxRunspaces] <Int32>] [-Oldest] [-DisableParallel] [-ExtendedOutput] [[-ExtendedInput] <Array>] [<CommonParameters>]
```
