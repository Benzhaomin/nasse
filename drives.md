`smartctl -i /dev/sdb`

```bash
smartctl 7.1 2019-12-30 r5022 [x86_64-linux-5.5.2-arch1-1] (local build)
Copyright (C) 2002-19, Bruce Allen, Christian Franke, www.smartmontools.org

=== START OF INFORMATION SECTION ===
Model Family:     WDC HGST Ultrastar He10
Device Model:     WDC WD80EMAZ-00WJTA0
Serial Number:    1EH-----
LU WWN Device Id: 5 000cca 27e------
Firmware Version: 83.H0A83
User Capacity:    8,001,563,222,016 bytes [8.00 TB]
Sector Sizes:     512 bytes logical, 4096 bytes physical
Rotation Rate:    5400 rpm
Form Factor:      3.5 inches
Device is:        In smartctl database [for details use: -P show]
ATA Version is:   ACS-2, ATA8-ACS T13/1699-D revision 4
SATA Version is:  SATA 3.2, 6.0 Gb/s (current: 6.0 Gb/s)
Local Time is:    Fri Feb  7 21:02:00 2020 CET
SMART support is: Available - device has SMART capability.
SMART support is: Enabled
Power mode is:    ACTIVE or IDLE
```

`smartctl -P /dev/sdb`

```bash
smartctl 7.1 2019-12-30 r5022 [x86_64-linux-5.5.2-arch1-1] (local build)
Copyright (C) 2002-19, Bruce Allen, Christian Franke, www.smartmontools.org

Drive found in smartmontools Database.  Drive identity strings:
MODEL:              WDC WD80EMAZ-00WJTA0
FIRMWARE:           83.H0A83
match smartmontools Drive Database entry:
MODEL REGEXP:       WDC WD(80|100)E[MZ]AZ-.*
FIRMWARE REGEXP:    .*
MODEL FAMILY:       WDC HGST Ultrastar He10
ATTRIBUTE OPTIONS:  022 Helium_Level
```

`hdparm -T /dev/sdb`

```bash
/dev/sdb:
 Timing cached reads:   9736 MB in  1.99 seconds = 4900.69 MB/sec
 Timing buffered disk reads: 596 MB in  3.00 seconds = 198.57 MB/sec
```

`hdparm -I /dev/sdb`

```bash
ATA device, with non-removable media
	Model Number:       WDC WD80EMAZ-00WJTA0
	Serial Number:      1EH-----
	Firmware Revision:  83.H0A83
	Transport:          Serial, ATA8-AST, SATA 1.0a, SATA II Extensions, SATA Rev 2.5, SATA Rev 2.6, SATA Rev 3.0; Revision: ATA8-AST T13 Project D1697 Revision 0b
Standards:
	Used: unknown (minor revision code 0x0029)
	Supported: 9 8 7 6 5
	Likely used: 9
Configuration:
	Logical		max	current
	cylinders	16383	16383
	heads		16	16
	sectors/track	63	63
	--
	CHS current addressable sectors:    16514064
	LBA    user addressable sectors:   268435455
	LBA48  user addressable sectors: 15628053168
	Logical  Sector size:                   512 bytes
	Physical Sector size:                  4096 bytes
	Logical Sector-0 offset:                  0 bytes
	device size with M = 1024*1024:     7630885 MBytes
	device size with M = 1000*1000:     8001563 MBytes (8001 GB)
	cache/buffer size  = unknown
	Form Factor: 3.5 inch
	Nominal Media Rotation Rate: 5400
Capabilities:
	LBA, IORDY(can be disabled)
	Queue depth: 32
	Standby timer values: spec'd by Standard, no device specific minimum
	R/W multiple sector transfer: Max = 16	Current = 16
	Advanced power management level: 164
	DMA: mdma0 mdma1 mdma2 udma0 udma1 udma2 udma3 udma4 udma5 *udma6
	     Cycle time: min=120ns recommended=120ns
	PIO: pio0 pio1 pio2 pio3 pio4
	     Cycle time: no flow control=120ns  IORDY flow control=120ns
Commands/features:
	Enabled	Supported:
	   *	SMART feature set
	    	Security Mode feature set
	   *	Power Management feature set
	   *	Write cache
	   *	Look-ahead
	   *	Host Protected Area feature set
	   *	WRITE_BUFFER command
	   *	READ_BUFFER command
	   *	NOP cmd
	   *	DOWNLOAD_MICROCODE
	   *	Advanced Power Management feature set
	    	Power-Up In Standby feature set
	   *	SET_FEATURES required to spinup after power up
	    	SET_MAX security extension
	   *	48-bit Address feature set
	   *	Device Configuration Overlay feature set
	   *	Mandatory FLUSH_CACHE
	   *	FLUSH_CACHE_EXT
	   *	SMART error logging
	   *	SMART self-test
	   *	Media Card Pass-Through
	   *	General Purpose Logging feature set
	   *	WRITE_{DMA|MULTIPLE}_FUA_EXT
	   *	64-bit World wide name
	   *	URG for READ_STREAM[_DMA]_EXT
	   *	URG for WRITE_STREAM[_DMA]_EXT
	   *	WRITE_UNCORRECTABLE_EXT command
	   *	{READ,WRITE}_DMA_EXT_GPL commands
	   *	Segmented DOWNLOAD_MICROCODE
	   *	unknown 119[6]
	    	unknown 119[7]
	   *	Gen1 signaling speed (1.5Gb/s)
	   *	Gen2 signaling speed (3.0Gb/s)
	   *	Gen3 signaling speed (6.0Gb/s)
	   *	Native Command Queueing (NCQ)
	   *	Host-initiated interface power management
	   *	Phy event counters
	   *	NCQ priority information
	   *	READ_LOG_DMA_EXT equivalent to READ_LOG_EXT
	    	Non-Zero buffer offsets in DMA Setup FIS
	   *	DMA Setup Auto-Activate optimization
	    	Device-initiated interface power management
	    	In-order data delivery
	   *	Software settings preservation
	    	unknown 78[7]
	    	unknown 78[10]
	    	unknown 78[11]
	   *	SMART Command Transport (SCT) feature set
	   *	SCT Write Same (AC2)
	   *	SCT Error Recovery Control (AC3)
	   *	SCT Features Control (AC4)
	   *	SCT Data Tables (AC5)
	   *	SANITIZE feature set
	   *	OVERWRITE_EXT command
	   *	reserved 69[3]
	   *	WRITE BUFFER DMA command
	   *	READ BUFFER DMA command
Security:
	Master password revision code = 65534
		supported
	not	enabled
	not	locked
		frozen
	not	expired: security count
	not	supported: enhanced erase
	832min for SECURITY ERASE UNIT.
Logical Unit WWN Device Identifier: 5000cca27-------
	NAA		: 5
	IEEE OUI	: 000cca
	Unique ID	: 27-------
Checksum: correct
```
