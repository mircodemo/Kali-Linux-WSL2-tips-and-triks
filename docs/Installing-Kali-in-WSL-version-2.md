# Installing Kali in WSL version 2

Perchè WSL versione 2

Requirement and installation

## Post installation

sudo apt update && sudo apt upgrade -y

[Kali Linux Metapackages | Kali Linux Documentation](https://www.kali.org/docs/general-use/metapackages/)

```bash
└─$ apt show kali-linux-headless
Package: kali-linux-headless
Version: 2021.1.10
Priority: optional
Section: metapackages
Source: kali-meta
Maintainer: Kali Developers <devel@kali.org>
Installed-Size: 18.4 kB
Depends: kali-linux-core, aircrack-ng, amass, arp-scan, arping | iputils-arping, binwalk, bluez, bluez-hcidump, bulk-extractor, bully, cadaver, cewl, chntpw, commix, crackmapexec, creddump7, crunch, cryptcat, davtest, dbd, dirb, dmitry, dns2tcp, dnschef, dnsenum, dnsrecon, enum4linux, exe2hexbat, exiv2, exploitdb, fierce, fping, gpp-decrypt, hash-identifier, hashcat, hashcat-utils, hashid, hping3, hydra, i2c-tools, ike-scan, impacket-scripts, inetsim, iodine, john, kismet, laudanum, lbd, macchanger, magicrescue, maltego, maskprocessor, masscan, metasploit-framework, mimikatz, mitmproxy, msfpc, nasm, nbtscan, ncrack, ncurses-hexedit, netdiscover, netsed, nfs-common, nikto, nmap, onesixtyone, passing-the-hash, patator, pdf-parser, pdfid, pipal, pixiewps, powersploit, proxychains4, proxytunnel, ptunnel, python3-impacket, python3-scapy, qsslcaudit, radare2, reaver, rebind, recon-ng, redsocks, responder, rsmangler, samdump2, sbd, scalpel, scrounge-ntfs, set, skipfish, sleuthkit, smbmap, snmpcheck, spiderfoot, spike, spooftooph, sqlmap, ssldump, sslscan, sslsplit, sslyze, statsprocessor, thc-ipv6, thc-pptp-bruter, theharvester, udptunnel, unix-privesc-check, voiphopper, wafw00f, wce, webshells, weevely, wfuzz, whatweb, wifite, windows-binaries, winexe, wordlists, wpscan, apache2, atftpd, axel, bind9-dnsutils, cifs-utils, clang, cryptsetup, cryptsetup-nuke-password, curlftpfs, default-mysql-server, dos2unix, ethtool, expect, gdisk, git, hashdeep, hotpatch, ifenslave, iw, minicom, miredo, mlocate, multimac, netmask, netsniff-ng, ngrep, openvpn, p7zip-full, php, php-mysql, pwnat, rake, rfkill, sakis3g, samba, screen, sendemail, snmp, snmpd, socat, sslh, stunnel4, swaks, tcpick, tcpreplay, telnet, testdisk, tftp, traceroute, unrar | unar, upx-ucl, vboot-kernel-utils, vboot-utils, vim | vim-nox, vlan, vpnc, whois
Recommends: python2, python-is-python2, offsec-awae-python2, bluez-firmware, firmware-amd-graphics, firmware-atheros, firmware-brcm80211, firmware-intel-sound, firmware-iwlwifi, firmware-libertas, firmware-linux, firmware-misc-nonfree, firmware-realtek, firmware-ti-connectivity, firmware-zd1211
Homepage: https://www.kali.org
Download-Size: 14.1 kB
APT-Manual-Installed: yes
APT-Sources: http://http.kali.org/kali kali-rolling/main amd64 Packages
Description: Kali Linux default headless system
 This is Kali Linux, the most advanced penetration testing and security
 auditing distribution.
 .
 This metapackage depends on all the applications that are included in
 official Kali Linux images and that don't require X11/GUI.

└─$ sudo apt install kali-linux-headless
```



```bash
sudo apt install -y zsh zsh-syntax-highlighting zsh-autosuggestions
cp /etc/skel/.zshrc ~/
```

sudo apt install neofetch cowsay lolcat

