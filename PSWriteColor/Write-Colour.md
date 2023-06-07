Write-Color
-----------




### Synopsis
Write-Color is a wrapper around Write-Host delivering a lot of additional features for easier color options.



---


### Description

Write-Color is a wrapper around Write-Host delivering a lot of additional features for easier color options.

It provides:
- Easy manipulation of colors,
- Logging output to file (log)
- Nice formatting options out of the box.
- Ability to use aliases for parameters



---


### Examples
#### EXAMPLE 1
```PowerShell
Write-Color -Text "Red ", "Green ", "Yellow " -Color Red,Green,Yellow
```

#### EXAMPLE 2
```PowerShell
Write-Color -Text "This is text in Green ",
                  "followed by red ",
                  "and then we have Magenta... ",
                  "isn't it fun? ",
                  "Here goes DarkCyan" -Color Green,Red,Magenta,White,DarkCyan
```

#### EXAMPLE 3
```PowerShell
Write-Color -Text "This is text in Green ",
                  "followed by red ",
                  "and then we have Magenta... ",
                  "isn't it fun? ",
                  "Here goes DarkCyan" -Color Green,Red,Magenta,White,DarkCyan -StartTab 3 -LinesBefore 1 -LinesAfter 1
```

#### EXAMPLE 4
```PowerShell
Write-Color "1. ", "Option 1" -Color Yellow, Green
Write-Color "2. ", "Option 2" -Color Yellow, Green
Write-Color "3. ", "Option 3" -Color Yellow, Green
Write-Color "4. ", "Option 4" -Color Yellow, Green
Write-Color "9. ", "Press 9 to exit" -Color Yellow, Gray -LinesBefore 1
```

#### EXAMPLE 5
```PowerShell
Write-Color -LinesBefore 2 -Text "This little ","message is ", "written to log ", "file as well." `
            -Color Yellow, White, Green, Red, Red -LogFile "C:\testing.txt" -TimeFormat "yyyy-MM-dd HH:mm:ss"
Write-Color -Text "This can get ","handy if ", "want to display things, and log actions to file ", "at the same time." `
            -Color Yellow, White, Green, Red, Red -LogFile "C:\testing.txt"
```

#### EXAMPLE 6
```PowerShell
Write-Color -T "My text", " is ", "all colorful" -C Yellow, Red, Green -B Green, Green, Yellow
Write-Color -t "my text" -c yellow -b green
Write-Color -text "my text" -c red
```

#### EXAMPLE 7
```PowerShell
Write-Color -Text "Testuję czy się ładnie zapisze, czy będą problemy" -Encoding unicode -LogFile 'C:\temp\testinggg.txt' -Color Red -NoConsoleOutput
```



---


### Parameters
#### **Text**

Text to display on screen and write to log file if specified.
Accepts an array of strings.






|Type        |Required|Position|PipelineInput|Aliases|
|------------|--------|--------|-------------|-------|
|`[String[]]`|false   |1       |false        |T      |



#### **Color**

Color of the text. Accepts an array of colors. If more than one color is specified it will loop through colors for each string.
If there are more strings than colors it will start from the beginning.
Available colors are: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White



Valid Values:

* Black
* DarkBlue
* DarkGreen
* DarkCyan
* DarkRed
* DarkMagenta
* DarkYellow
* Gray
* DarkGray
* Blue
* Green
* Cyan
* Red
* Magenta
* Yellow
* White






|Type              |Required|Position|PipelineInput|Aliases                      |
|------------------|--------|--------|-------------|-----------------------------|
|`[ConsoleColor[]]`|false   |2       |false        |C<br/>ForegroundColor<br/>FGC|



#### **BackGroundColor**

Color of the background. Accepts an array of colors. If more than one color is specified it will loop through colors for each string.
If there are more strings than colors it will start from the beginning.
Available colors are: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White



Valid Values:

* Black
* DarkBlue
* DarkGreen
* DarkCyan
* DarkRed
* DarkMagenta
* DarkYellow
* Gray
* DarkGray
* Blue
* Green
* Cyan
* Red
* Magenta
* Yellow
* White






|Type              |Required|Position|PipelineInput|Aliases  |
|------------------|--------|--------|-------------|---------|
|`[ConsoleColor[]]`|false   |3       |false        |B<br/>BGC|



#### **StartTab**

Number of tabs to add before text. Default is 0.






|Type     |Required|Position|PipelineInput|Aliases|
|---------|--------|--------|-------------|-------|
|`[Int32]`|false   |4       |false        |Indent |



#### **LinesBefore**

Number of empty lines before text. Default is 0.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |5       |false        |



#### **LinesAfter**

Number of empty lines after text. Default is 0.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |6       |false        |



#### **StartSpaces**

Number of spaces to add before text. Default is 0.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |7       |false        |



#### **LogFile**

Path to log file. If not specified no log file will be created.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |8       |false        |L      |



#### **DateTimeFormat**

Custom date and time format string. Default is yyyy-MM-dd HH:mm:ss






|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|false   |9       |false        |DateFormat<br/>TimeFormat|



#### **LogTime**

If set to $true it will add time to log file. Default is $true.






|Type       |Required|Position|PipelineInput|Aliases     |
|-----------|--------|--------|-------------|------------|
|`[Boolean]`|false   |10      |false        |LogTimeStamp|



#### **LogRetry**

Number of retries to write to log file, in case it can't write to it for some reason, before skipping. Default is 2.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |11      |false        |



#### **Encoding**

Encoding of the log file. Default is Unicode.



Valid Values:

* unknown
* string
* unicode
* bigendianunicode
* utf8
* utf7
* utf32
* ascii
* default
* oem






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |12      |false        |



#### **ShowTime**

Switch to add time to console output. Default is not set.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **NoNewLine**

Switch to not add new line at the end of the output. Default is not set.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **NoConsoleOutput**

Switch to not output to console. Default all output goes to console.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[Switch]`|false   |named   |false        |HideConsole|





---


### Notes
Understanding Custom date and time format strings: https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings
Project support: https://github.com/EvotecIT/PSWriteColor
Original idea: Josh (https://stackoverflow.com/users/81769/josh)



---


### Syntax
```PowerShell
Write-Color [[-Text] <String[]>] [[-Color] {Black | DarkBlue | DarkGreen | DarkCyan | DarkRed | DarkMagenta | DarkYellow | Gray | DarkGray | Blue | Green | Cyan | Red | Magenta | Yellow | White}] [[-BackGroundColor] {Black | DarkBlue | DarkGreen | DarkCyan | DarkRed | DarkMagenta | DarkYellow | Gray | DarkGray | Blue | Green | Cyan | Red | Magenta | Yellow | White}] [[-StartTab] <Int32>] [[-LinesBefore] <Int32>] [[-LinesAfter] <Int32>] [[-StartSpaces] <Int32>] [[-LogFile] <String>] [[-DateTimeFormat] <String>] [[-LogTime] <Boolean>] [[-LogRetry] <Int32>] [[-Encoding] <String>] [-ShowTime] [-NoNewLine] [-NoConsoleOutput] [<CommonParameters>]
```
