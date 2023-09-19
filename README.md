# shadow detect firmware OTA updates

two files: 

version.txt (contains the current version number)
firmware.bin (contains the compiled firmware for the version)

scans currently implemented:

subnet size calcualtor - takes the gateway ip and subnet mask, calculates beginning and end ip addresses of network
arp_scan - sends out an arp query for every ip address in the network, gathers mac addresses (used in all other scans from then on)
mdns_broadcast - listens for mdns broadcast packets, extrracts PTR and TXT information, periodically uploads to cloud
ssdp_broadcast - listens for ssdp broadcast packets, periodically uploads to cloud
ssdp_scan - probes for ssdp services
ssdp_tv_scan - probes for ssdp dial services
ssdp_location - on finding location info on ssdp or ssdp_tv scans, fetches the location info and parses
MDNs / Bonjour services scan - searches the network for specific bonjour / mdns services
NBNS scan - queries and collects the NetBios machine names from the network
iphone_scan - checks all devices returned by arp_scan for open port 62078
port_scan - checks all devices returned by arp_scan for open port 9, 21, 22, 23, 25, 53, 67, 68, 80, 88, 110, 135, 137, 138, 139, 143, 153, 161, 162, 220, 443, 445, 587, 8080, 993, 995, 1080, 1194, 1900, 3306, 62078




-------
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