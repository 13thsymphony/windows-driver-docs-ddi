---
UID: NS.GNSSDRIVER.PGNSS_CHIPSETINFO
title: PGNSS_CHIPSETINFO
author: windows-driver-content
description: This structure defines the specific data elements associated with the GNSS hardware.
old-location: sensors\gnss_chipsetinfo.htm
old-project: sensors
ms.assetid: DE45805C-09E6-44B8-A4DA-BF73EC444AA9
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PGNSS_CHIPSETINFO, GNSS_CHIPSETINFO, *PGNSS_CHIPSETINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_CHIPSETINFO
req.alt-loc: gnssdriver.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# PGNSS_CHIPSETINFO structure



## -description
This structure defines the specific data elements associated with the GNSS hardware.


## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  WCHAR ManufacturerID[25];
  WCHAR HardwareID[25];
  WCHAR FirmwareVersion[20];
  BYTE  Unused[512];
} GNSS_CHIPSETINFO, *PGNSS_CHIPSETINFO;
````


## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field ManufacturerID[25]

String containing an identifier for the manufacturer.

### -field HardwareID[25]

String containing an identifier for the specific GNSS chipset or combo chipset.

### -field FirmwareVersion[20]

Version for the firmware for the. This would be a string, typically of the format NNNN.NNNN.NNNN.NNNN.

### -field Unused[512]

Padding buffer.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>