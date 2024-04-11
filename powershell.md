# Powershell



## Config File

powershell.config.json



### Location

#### General Installation
**$PSHOME** <br>
<C:\Windows\System32\WindowsPowerShell\v1.0>

#### Specific User
**$PROFILE.CurrentUserCurrentHost** <br>
<C:\Users\Krzysztof\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1>



### Allow Unsigned Scripts
start-process powershell -verb runas 
(ADMIN)

Set-ExecutionPolicy RemoteSigned 
(allow unsigned scripts, i.e. also your configuration file)
powershell.config.json

