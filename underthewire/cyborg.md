

The password for cyborg3 is the host A record IP address for CYBORG718W100N PLUS the name of the file on the desktop.  
Resolve-DnsName -Name CYBORG718W100N
ls  
`172.31.45.167_ipv4`  
  
The password for cyborg4 is the number of users in the Cyborg group within Active Directory PLUS the name of the file on the desktop.  
Get-ADGroupMember -Identity cyborg |measure  
ls
`88_objects`  
  
The password for cyborg5 is the PowerShell module name with a version number of 8.9.8.9 PLUS the name of the file on the desktop.
Get-Module -ListAvailable
ls
`bacon_eggs`

The password for cyborg6 is the last name of the user who has logon hours set on their account PLUS the name of the file on the desktop.  f
Get-ADUser -Property logonhours -Filter 'logonhours -like "*"'  
ls  
`rowray_timer`  

The password for cyborg7 is the decoded text of the string within the file on the desktop.  
gc .\cypher.txt | %{ [Text.Encoding]::ASCII.Getstring([convert]::FromBase64String($_)) }       # good enough
`cybergeddon`  
  
The password for cyborg8 is the executable name of a program that will start automatically when cyborg7 logs in.  
Get-CimInstance Win32_StartupCommand  
`skynet`  
# The hint mentions the regkey. So they were going for following solution  
Get-Item HKcu:\SOFTWARE\Microsoft\Windows\CurrentVersion\Run  
  
The password for cyborg9 is the Internet zone that the picture on the desktop was downloaded from.  
Get-item -Stream * .\1_qs5nwlcl7f_-SwNlQvOrAw.png
Get-Content -Stream Zone.Identifier .\1_qs5nwlcl7f_-SwNlQvOrAw.png  
`4`  

The password for cyborg10 is the first name of the user with the phone number of 876-5309 listed in Active Directory PLUS the name of the file on the desktop.
Get-ADUser -Filter 'telephoneNumber -like "*876-5309*"'  
ls  
`onita99`  
  
The password for cyborg11 is the description of the Applocker Executable deny policy for ill_be_back.exe PLUS the name of the file on the desktop.  
Get-AppLockerPolicy -Effective | select -ExpandProperty RuleCollections  
`terminated!99`  
  
The password for cyborg12 is located in the IIS log. The password is not Mozilla or Opera.  
gc C:\inetpub\logs\logfiles\w3svc1\u_ex160413.log |? {$_ -notmatch 'Opera|Mozilla'}  
`2016-04-13 04:14:12 W3SVC1 Century 172.31.45.65 GET / - 80 - 172.31.45.65 HTTP/1.1 LordHelmet/5.0+(CombTheDesert)+Password+is:spaceballs - - century.underthewire.tech 200 0 0 925 118 0`  

The password for cyborg13 is the first four characters of the base64 encoded full path to the file that started the i_heart_robots service PLUS the name of the file on the desktop.
Get-CimInstance Win32_Service -Filter 'name like "i_heart_robots"' | select *  
[convert]::ToBase64String([system.text.encoding]::Unicode.GetBytes('c:\windows\system32\cmd.exe') )  
ls  
`ywa6_heart`  
  
The password cyborg14 is the number of days the refresh interval is set to for DNS aging for the underthewire.tech zone PLUS the name of the file on the desktop.  
Get-DnsServerZoneAging -Name underthewire.tech  
gci  
`22_days`  
  
The password for cyborg15 is the caption for the DCOM application setting for application ID {59B8AFA0-229E-46D9-B980-DDA2C817EC7E} PLUS the name of the file on the desktop.  
Get-CimInstance Win32_DCOMApplicationSetting | ? {$_.AppID -match '59B8AFA0-229E-46D9-B980-DDA2C817EC7E'}  
gci  
`propshts_objects`  

  
