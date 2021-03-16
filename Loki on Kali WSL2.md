# Loki on Kali WSL2

## Introduction

### Loki - Simple IOC Scanner

Scanner for Simple Indicators of Compromise

Detection is based on four detection methods:

1. File Name IOC
   Regex match on full file path/name
2. Yara Rule Check
   Yara signature match on file data and process memory
3. Hash check
   Compares known malicious hashes (MD5, SHA1, SHA256) with scanned files
4. C2 Back Connect Check
   Compares process connection endpoints with C2 IOCs (new since version v.10)

You can find all the information in the official repo: [Neo23x0/Loki: Loki - Simple IOC and Incident Response Scanner (github.com)](https://github.com/Neo23x0/Loki)

## Install

Loky is a pyhton script so check your installed version.

Download the latest version from the [release](https://github.com/Neo23x0/Loki/releases) page and extract it.

```bash
sudo wget https://github.com/Neo23x0/Loki/archive/0.40b_02.tar.gz
sudo tar -xf 0.40b_02.tar.gz
cd Loki-0.40b_02
```

Install some requirements:

```bash
sudo pip install -r requirements.txt
sudo pip install rfc5424-logging-handler
sudo pip install yara-python
```

Loki need the presence of the symlink /ect/mtab so we need to create it:

```bash
ln -s /proc/mounts /etc/mtab
```

Now we must run loki-upgrader.py to retrieve the latest signature base repository.

```bash
sudo python3.9 loki-upgrader.py
```

And finally we can run Loky.

```bash
sudo python3.9 loki.py -h
```

![image-20210316234334156](C:\Users\mdemo\AppData\Roaming\Typora\typora-user-images\image-20210316234334156.png)

## Run a test

Before try to run a full scan on a target machine we can test our installation with some file in the test folder using this command.

```bash
sudo python3.9 loki.py -p test --onlyrelevant --nolog
```

If all working properly you should get Loki presentation page and some alert:

![image-20210316234828165](C:\Users\mdemo\AppData\Roaming\Typora\typora-user-images\image-20210316234828165.png)