## Run a Windows 10 VM 

- Some examples can be downloaded from Microsoft

## Launch Winpmem

## Copy the dump to your analysis machine

## Analyze with Volatility 

- Verify the profile is included in Volatility default profile list

### Install Volatility 3.0 

```
cd /opt/
mkdir /opt/forensics/
git clone https://github.com/volatilityfoundation/volatility3.git
pip3 install -r requirements.txt
curl https://downloads.volatilityfoundation.org/volatility3/symbols/windows.zip
cp windows.zip  /usr/local/lib/python3.8/dist-packages/volatility3-2.4.0-py3.8.egg/volatility3/symbols/
```

Wait for cache to update (first launch)...
### A few examples command to launch with Volatility (3.0 here) 

```
# Get all modules options 
vol --info
```

#### Kdbgscan - Info on Windows image
```
# vol -f memdump_Win10x64_15063.mem windows.info
```

#### Processes information
```
vol.py -f memdump_Win10x64_15063.mem pslist
vol.py -f memdump_Win10x64_15063.mem pstree
vol.py -f memdump_Win10x64_15063.mem windows.cmdline.cmdline
# vol -f Snapshot19.vmem windows.registry.userassist.UserAssist
```

#### Specific process information 
```
vol.py -f memdump_Win10x64_15063.mem windows.dlllist.dlllist --pid [PID]
vol.py -f memdump_Win10x64_15063.mem windows.handles.handles --pid [PID]
```
#### Network Information
```
vol.py -f memdump_Win10x64_15063.mem windows.netscan
vol.py -f memdump_Win10x64_15063.mem windows.netstat
```

#### Finding evil 
```
vol.py -f memdump_Win10x64_15063.mem malfind
vol.py -f memdump_Win10x64_15063.mem yarascan -y [YARA rule, ex: suspicious_strings]
./vol.py -f file.dmp windows.driverirp.DriverIrp #Driver IRP hook detection
./vol.py -f file.dmp windows.ssdt.SSDT #Check system call address from unexpected addresses
```

#### Getting passwods

```
# vol -f Snapshot6.vmem windows.lsadump.Lsadump
# vol -f Snapshot6.vmem windows.hashdump.Hashdump

```
#### Dump content
```
# Dump files associated with a PID 
vol -f Snapshot19.vmem windows.dumpfiles.DumpFiles --pid 1920
vol -f Snapshot19.vmem -o dumpDir windows.memmap --dump --pid 1920
```

#### Create Timeline (sweet !)

```
# vol -f Snapshot19.vmem timeliner.Timeliner
```

#### Persistence / Autoruns

Download it from [https://github.com/tomchop/volatility-autoruns](https://github.com/tomchop/volatility-autoruns)

```
volatility --plugins=volatility-autoruns/ --profile=WinXPSP2x86 -f file.dmp autoruns
```
## Bulk Extractor 

### Install

```
cd /opt/
git clone --recursive https://github.com/simsong/bulk_extractor.git
echo -ne '\n' | bash bulk_extractor/etc/CONFIGURE_UBUNTU20LTS.bash
cd bulk_extractor/
./configure
make
make install
```

## Evtxtract

### Install

```
pip install evtxtract
```

### Use 
```
evtxtract [file.mem] > outEvents.xml 
```
