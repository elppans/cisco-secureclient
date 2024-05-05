# Instructions

1. Download the latest secureclient from here: https://software.cisco.com/download/home/286330811/type/282364313/release/5.1.1.42
2. Copy the tarball to `$HOME/work/cisco-secureclient/` or change the `source`
   variable in PKGBUILD to point to the location of your downloaded tarball
3. You may have to remove `/opt/cisco/secureclient/lib` if there was a previous failed upgrade of secureclient
4. Run `makepkg -si`
5. Check the status of the vpn service with `systemctl status
   vpnagentd.service`. You may have to start it using `systemctl start
   vpnagentd.service`
6. Run `cisco-secureclient&` or start it using the GUI

Link Version:
https://cios.dhitechnical.com/Cisco_Firewall_ASA_FTD/Cisco%20Secure%20Client%205.x/
