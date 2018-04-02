---
UID: NF:ioaccess.WRITE_PORT_USHORT
title: WRITE_PORT_USHORT function
author: windows-driver-content
description: The WRITE_PORT_USHORT routine writes a USHORT value to the specified port address.
old-location: kernel\write_port_ushort.htm
old-project: kernel
ms.assetid: 60145cf3-62cb-4165-8536-f1546b9623dd
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: WRITE_PORT_USHORT, WRITE_PORT_USHORT routine [Kernel-Mode Driver Architecture], k103_28fd826b-359f-4111-91d0-426fb2d2a62b.xml, kernel.write_port_ushort, wdm/WRITE_PORT_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ioaccess.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: Hal.lib
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hal.lib
-	Hal.dll
api_name:
-	WRITE_PORT_USHORT
product:
- Windows
targetos: Windows
req.typenames: IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS, IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS
---


# WRITE_PORT_USHORT function
The <b>WRITE_PORT_USHORT</b> routine writes a USHORT value to the specified port address.

## Syntax

```
void WRITE_PORT_USHORT(
  PVOID Port,
  ULONG Value
);
```

## Parameters

`Port`

Pointer to the port, which must be a mapped memory range in I/O space.

`Value`

Specifies a USHORT value to be written to the port.


## Return Value

None

## Remarks

Callers of <b>WRITE_PORT_USHORT</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ioaccess.h (include Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h) |
| **Library** | Hal.lib |
| **IRQL** | Any level (see Remarks section) |