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

## Requirements

Loky is a pyhton based script so check your installed version of pip and pyhton.

```bash
└─$ pip --version
pip 20.3.4 from /usr/lib/python3/dist-packages/pip (python 3.9)

└─$ python --version
Python 2.7.18

└─$ python3 --version
Python 3.9.2
```

In this case we have pip linked to python 3.9. So we use python3 command for the next steps.

Install some requirements:

```bash
sudo pip install yara-python netaddr psutil pylzma rfc5424-logging-handler
```

Loki need the presence of the symlink /ect/mtab so we need to create it:

```bash
sudo ln -s /proc/mounts /etc/mtab
```



## Install

Download the latest version from the [release](https://github.com/Neo23x0/Loki/releases) page and extract it.

```bash
sudo wget https://github.com/Neo23x0/Loki/archive/0.40b_02.tar.gz
sudo tar -xf 0.40b_02.tar.gz
sudo rm 0.40b_02.tar.gz
cd Loki-0.40b_02
```

Now we must run loki-upgrader.py to retrieve the latest signature base repository.

```bash
sudo python3 loki-upgrader.py
```

And finally we can run Loky.

```bash
sudo python3 loki.py -h
```

![image-20210316234334156](C:\Users\mdemo\AppData\Roaming\Typora\typora-user-images\image-20210316234334156.png)

## Run a test

Before try to run a full scan on a target machine we can test our installation with some file in the test folder using this command.

```bash
sudo python3 loki.py -p test --onlyrelevant --nolog
```

If all working properly you should get Loki presentation page and some alert:

![image-20210316234828165](C:\Users\mdemo\AppData\Roaming\Typora\typora-user-images\image-20210316234828165.png)