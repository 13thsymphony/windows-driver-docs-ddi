---
UID: NS.GNSSDRIVER.PGNSS_SELFTESTCONFIG
title: PGNSS_SELFTESTCONFIG
author: windows-driver-content
description: This structure defines the specific data elements associated with a carrier wave test results returned from the driver.
old-location: sensors\gnss_selftestconfig.htm
old-project: sensors
ms.assetid: DE0D4A9A-F85D-4AA4-8A21-1BEC86837444
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PGNSS_SELFTESTCONFIG, *PGNSS_SELFTESTCONFIG, GNSS_SELFTESTCONFIG
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
req.alt-api: GNSS_SELFTESTCONFIG
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

# PGNSS_SELFTESTCONFIG structure



## -description
This structure defines the specific data elements associated with a carrier wave test results returned from the driver.


## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG TestType;
  BYTE  Unused[512];
  ULONG InBufLen;
  BYTE  InBuffer[ANYSIZE_ARRAY];
} GNSS_SELFTESTCONFIG, *PGNSS_SELFTESTCONFIG;
````


## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field TestType

The type of self-test requested.

### -field Unused[512]

Padding buffer.

### -field InBufLen

The length of the buffer for passing in any additional information about the self-test.

### -field InBuffer[ANYSIZE_ARRAY]

The buffer that will contain the additional information about the self-test.

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