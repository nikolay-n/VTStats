
# VTStats
VT Enterprise Quotas and Usage Statistics macOS menubar app. 
The purpose of app to monitor Virustotal Intelligence Enterprise resources usage. Uses https://www.virustotal.com/api/v3/users/api-key/overall_quotas API to fetch statistics. Currently only grabs inherited from VTI group usage data.
## Instalation
     mkdir ~/Tools; cd ~/Tools
     
     git clone https://github.com/nikolay-n/VTStats.git
     
     cd ~/Tools/VTStats
     
     # copy LaunchAgent template
     cp ./LaunchAgents/com.gorelics.VTStats.plist ~/Library/LaunchAgents/
     
     # replace /absolute/path/to/vtstats with real path
     /usr/libexec/PlistBuddy -c "Set :Program /absolute/path/to/vtstats" ~/Library/LaunchAgents/com.gorelics.VTStats.plist
     
     # load LaunchAgent
     launchctl load -w ~/LaunchAgents/com.gorelics.VTStats.plist
	 
	 # start or stop
     launchctl stop com.gorelics.VTStats
     launchctl start com.gorelics.VTStats
## Features

 - uses macOS standard python 2.7 distribution, doesn't requires any other environment to setup, includes https://github.com/jaredks/rumps python library
 - shows menubar menu with usage statistics
 - automatically fetches statistics using VT API in specified interval or manually
 - shows usage notifications when % of any VTI resources was used
 - displays usage colors depending on amount of resources used
