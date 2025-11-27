century1:century1  
The password for Century2 is the build version of the instance of PowerShell installed on this system.  
$PSVersionTable  
`10.0.14393.8422`  
  
The password for Century3 is the name of the built-in cmdlet that performs the wget like function within PowerShell PLUS the name of the file on the desktop.  
PS C:\users\century2\desktop> Get-ChildItem  
`443`  
Get-Alias wget  
`wget -> Invoke-WebRequest`  
  
The password for Century4 is the number of files on the desktop.  
Get-ChildItem | Measure-Object  
`123`  

The password for Century5 is the name of the file within a directory on the desktop that has spaces in its name.  
tree /f        # not really Powershell, but gives a quick nice overview.
`15768`  

The password for Century6 is the short name of the domain in which this system resides in PLUS the name of the file on the desktop.
"$((Get-ADDomain).NetBiosName)$((Get-ChildItem).Name)"  
`underthewire3347`  
  
The password for Century7 is the number of folders on the desktop.  
Get-ChildItem -Directory | Measure-Object  
`197`  

The password for Century8 is in a readme file somewhere within the contacts, desktop, documents, downloads, favorites, music, or videos folder in the user’s profile.  
find file with - PS C:\users\century7\desktop> tree .. /f  
read file with - PS C:\users\century7\desktop> Get-Content ..\Downloads\Readme.txt  
`7points`  

The password for Century9 is the number of unique entries within the file on the desktop.  
Get-Content .\unique.txt | Sort-Object -Unique | Measure-Object | Select-Object -ExpandProperty Count  
`696`  

The password for Century10 is the 161st word within the file on the desktop.  
Get-Content .\Word_File.txt -Delimiter ‘ ’ -TotalCount 161
`pierid`  

The password for Century11 is the 10th and 8th word of the Windows Update service description combined PLUS the name of the file on the desktop.  
(Get-CimInstance Win32_Service -Filter "Name like '%wuauserv%'" -Property Description).Description -split ' ' | Select-Object -Index 9,11  
`updates`  
`windows`  
Get-ChildItem
`110`
Result `windowsupdates110`  

The password for Century12 is the name of the hidden file within the contacts, desktop, documents, downloads, favorites, music, or videos folder in the user’s profile.  
Get-ChildItem -Hidden -File -Recurse ..\ -ErrorAction Ignore -Exclude desktop.ini  
`secret_sauce`

The password for Century13 is the description of the computer designated as a Domain Controller within this domain PLUS the name of the file on the desktop.  
find Domain Controller - Get-ADDomainController  
get Description - Get-ADObject 'CN=UTW,OU=Domain Controllers,DC=underthewire,DC=tech' -Properties Description'  
`i_authenticate`  
ls  
`_things`  
result `i_authenticate_things`  

The password for Century14 is the number of words within the file on the desktop.  
Get-Content .\countmywords | Measure-Object -Word  
`755`  
  
The password for Century15 is the number of times the word “polo” appears within the file on the desktop.  
(gc .\countpolos) -split ' ' -like 'polo' | Measure-Object
`153`  
NOTE: Figure out why variants with 'Get-Content -Delimiter ' ')' did not work.
