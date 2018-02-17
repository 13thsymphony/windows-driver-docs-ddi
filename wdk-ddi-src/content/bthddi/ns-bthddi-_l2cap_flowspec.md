---
UID: NS:bthddi._L2CAP_FLOWSPEC
title: "_L2CAP_FLOWSPEC"
author: windows-driver-content
description: This structure reserved for future use.
old-location: bltooth\l2cap_flowspec.htm
old-project: bltooth
ms.assetid: 1b8a3181-45eb-4c35-9ccc-d6fe1f7ca92c
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.l2cap_flowspec, L2CAP_FLOWSPEC structure [Bluetooth Devices], L2CAP_FLOWSPEC Structure structure [Bluetooth Devices], bthddi/PL2CAP_FLOWSPEC, bthddi/L2CAP_CONFIG_VALUE_RANGE, PL2CAP_FLOWSPEC, *PL2CAP_FLOWSPEC, L2CAP_FLOWSPEC Structure, _L2CAP_FLOWSPEC, bth_structs_2d7077bd-6328-4d54-9238-f463fad371d6.xml, PL2CAP_FLOWSPEC structure pointer [Bluetooth Devices], L2CAP_FLOWSPEC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthddi.h
apiname:
-	L2CAP_FLOWSPEC
product: Windows
targetos: Windows
req.typenames: L2CAP_FLOWSPEC, *PL2CAP_FLOWSPEC
---

# _L2CAP_FLOWSPEC structure
This structure reserved for future use.

## Syntax
````
typedef struct _L2CAP_FLOWSPEC {
  UCHAR Flags;
  UCHAR ServiceType;
  ULONG TokenRate;
  ULONG TokenBucketSize;
  ULONG PeakBandwidth;
  ULONG Latency;
  ULONG DelayVariation;
} L2CAP_FLOWSPEC, *PL2CAP_FLOWSPEC;
````

## Members


`DelayVariation`

Reserved.

`Flags`

Reserved.

`Latency`

Reserved.

`PeakBandwidth`

Reserved.

`ServiceType`

Reserved.

`TokenBucketSize`

Reserved.

`TokenRate`

Reserved.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |