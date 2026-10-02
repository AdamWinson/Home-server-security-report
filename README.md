# Home server security report

This report documents a security assessment of a personally-owned home server, configured to host a Jellyfin media server and a public-facing webpage for a custom domain. Remote access to the server is managed through Tailscale, a WireGuard-based VPN, which was implemented to restrict administrative access to trusted devices rather than exposing management interfaces directly to the internet.

The objective of this assessment was to evaluate the server's security posture from an external attacker's perspective, using industry-standard reconnaissance and vulnerability-scanning tools.

### Scanning 
The first thing I needed to do was to scan for open ports on the networks and i did thins through using a tool called Nmap. An initial run of this was done through the VPN as a sort of "Internal network scan" using the command:

'nmap -sV -sC -p- -T4 <server-tailscale-ip>'

'-sV' grabs the service info, '-sC' uses Nmaps default scripts, '-p' scans all 65535 ports and-T4 makes the scan more aggressive & detectable but far quicker (this is okay as its my own server) 
