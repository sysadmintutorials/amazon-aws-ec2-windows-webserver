<powershell>
## Install IIS Web Server
Install-WindowsFeature -name Web-Server -IncludeManagementTools
## Change directory to wwwroot
cd \inetpub\wwwroot
## Delete IIS default html files
remove-item iisstart.*
## Grab IP info into variables
$localipv4 = invoke-restmethod -uri  http://169.254.169.254/latest/meta-data/local-ipv4
$publicipv4 = invoke-restmethod -uri  http://169.254.169.254/latest/meta-data/public-ipv4
$publichostname = invoke-restmethod -uri  http://169.254.169.254/latest/meta-data/public-hostname
## Grab Server info into variables
$hostname = hostname
$instancetype = invoke-restmethod -uri  http://169.254.169.254/latest/meta-data/instance-type
$operatingsystem = (Get-CimInstance -ClassName Win32_OperatingSystem).Caption
## Create new index.html file
New-Item index.html
$filename = 'index.html'
## Write info to index.html
Add-Content $filename "<br>"
Add-Content $filename "<h2><b>Sysadmintutorials EC2 Windows Demo</b></h2>"
Add-Content $filename "<b>Your Server Hostname is:</b> "
Add-Content $filename $hostname
Add-Content $filename "<br>"
Add-Content $filename "<b>Your Instance Type is:</b> "
Add-Content $filename $instancetype
Add-Content $filename "<br>"
Add-Content $filename "<b>Your Operating System is:</b> "
Add-Content $filename $operatingsystem
Add-Content $filename "<br>"
Add-Content $filename "<b>Your Internal IP Address is:</b> "
Add-Content $filename $localipv4
Add-Content $filename "<br>"
Add-Content $filename "<b>Your External IP Address is:</b> "
Add-Content $filename $publicipv4
Add-Content $filename "<br>"
Add-Content $filename "<b>Your Public DNS Address is:</b> "
Add-Content $filename $publichostname
</powershell>
