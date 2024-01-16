# shadow detect firmware OTA updates

two files: 

version.txt (contains the current version number)
firmware.bin (contains the compiled firmware for the version)

scans currently implemented:

subnet size calcualtor - takes the gateway ip and subnet mask, calculates beginning and end ip addresses of network
arp_scan - sends out an arp query for every ip address in the network, gathers mac addresses (used in all other scans from then on)
mdns_broadcast - [unused] listens for mdns broadcast packets, extrracts PTR and TXT information, periodically uploads to cloud
ssdp_broadcast - [unused] listens for ssdp broadcast packets, periodically uploads to cloud
ssdp_scan - probes for ssdp services
ssdp_tv_scan - probes for ssdp dial services
ssdp_location - on finding location info on ssdp or ssdp_tv scans, fetches the location info and parses
MDNs / Bonjour services scan - searches the network for specific bonjour / mdns services
    http,workstation,smb,ftp,ipp,printer,amzn-alexa,amzn-wplay,spotify-connect,pdl-datastream,googlecast,googlezone,nintendoswitch,matter,visiocast,afpovertcp,airport,appletv,appletv-pair,airplay,companion-link,tivo-remote,device-info,dns-sd,dns-update,domain,honeywell-vid,sip,apple-mobdev2,mediaremotetv,companion-link,raop,sleep-proxy,homekit,touch-able,dns-sd,matterrc
NBNS scan - queries and collects the NetBios machine names from the network
SMB version scan - queries the available SMB versions
SMB NATIVEOS scan - queries the native_os version on smb services
SMB GSS-API build number scan
iphone_scan - checks all devices returned by arp_scan for open port 62078
sip_scan - checks all devices returned by arp_scan for open ports 5060 and 5061
port_scan - checks all devices returned by arp_scan for open port 9, 21, 22, 23, 25, 53, 67, 68, 80, 88, 110, 135, 137, 138, 139, 143, 153, 161, 162, 220, 443, 445, 587, 8080, 993, 995, 1080, 1194, 1900, 3306, 5060, 5061 62078
hostname scan [dns over mdns]
Wifi AP Scan [unused]

---------------
v210 - Upgrade to arduinoJson7 / SW_VER sent in every request
v202 - SSDP scan memory increase and rewrite
v201 - comment out SIP scan for testing
v200 - separating architecture for the various boards and modifying update procedure
v127 - fixing crashes, adding support for board with built-in LED
v126 - separate ssdp + ssdp TV scans again as its not picking up as much with the combined scan
v125 - increase buffer for login token as causeing crashes in boxes
v124 - dont return on upload error, reset box / clear doc on upload fail
v123 - dont send blank hostnames
v122 - ARP scan fix issues
v121 - HOSTNAME scan [dns query over mdns]
v120 - SSDP location scan fix issues
v119 - dont upload location response if its zeros
v118 - dont upload smb scan if empty - alternative
v117 - dont upload smb scan if empty
v116 - fixing a panic()
v115 - memory optimisations
v114 - check if its possible to match wifimanager and app themes (** partially - we can add custom css and get a close-enough match)
v112 - small bugfix on ssdp upload / overflow if too many scans
v111 - move to platformio and separate code
v110 - mac address in every scan
v109 - SMB2 GSS-API Build number scan!
v108 - bug fixes against 105 / upload ssdp individually
v107 - bug fixes against 105 / upload ssdp individually
v106 - bug fixes against 105 / upload ssdp individually
v105 - NBNS, ssdp, ssdp location data clearing before uploads
v104 - SMB version, SMB NativeOS, NBNS fixes
v103 - SMB version scan, SMB NativePS scan, NBNS scan fixes
v102 - sip scan
v101 - always send up gateway_ip address with the scans
v100 - dynamic company_name in scan_upload function
v99 - small internal http server to get ip address for requesting machine (for web navgator agent os_version determination)
v98 - change how SSDP scans are packaged
v97 - change how SSDP scans are uploaded to fix bug
v96 - minor bugfixes against v92
v95 - minor bugfixes against v92
v94 - minor bugfixes against v92
v93 - minor bugfixes against v92
v92 - Bonjour Services Scan rewrite - queries and collects the bnojour / mDNS machine names from the network; MDNS PTR and TXT scan - extracts info from mDNS responses on network via library 
v91 - NBNS scan - queries and collects the NetBios machine names from the network; MDNS PTR and TXT scan - extracts info from mDNS responses on network
v90 - dont downlaod the location file form ssdp services multiple times
v89 - changing format of portscan data array[port => state] and "ssdp/mdns broadcast/ssdp broadcast" ip, mac + location from an array in an array to key=>value json objects 
v88 - turning ssdp locations and broadcasts back into individual uploads
v87 - bundling ssdp locations and broadcasts into single uploads
v86 - lots of incremental changes and tweaks
v85 - separate ssdp broadcast, mdns broadcast ssdp scans
v84 - separate ssdp broadcast, mdns broadcast ssdp scans
v83 - separate ssdp broadcast, mdns broadcast ssdp scans
v82 - ssdp scan tweaking
v81 - calculate_subnet, ssdp scan tweaking
v80 - rewrite of ssdp json formating to use maps
v79 - rewrite of ssdp json formating to use maps
v78 - rewrite of ssdp json formating to use maps
v77 - rewrite of ssdp json formating to use maps
v76 - rewrite of ssdp json formating to use maps
v75 - rewrite of ssdp json formating to use maps
v74 - rewrite of ssdp json formating to use maps

v73 - testing out ota via github
v72 - testing out ota via github
v71 - last roger build, first repo commits around here
... roger builds
v1 initial build (w/ roger)