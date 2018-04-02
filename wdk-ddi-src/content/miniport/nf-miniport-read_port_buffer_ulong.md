---
UID: NF:miniport.READ_PORT_BUFFER_ULONG
title: READ_PORT_BUFFER_ULONG function
author: windows-driver-content
description: The READ_PORT_BUFFER_ULONG routine reads a number of ULONG values from the specified port address into a buffer.
old-location: kernel\read_port_buffer_ulong.htm
old-project: kernel
ms.assetid: a63028d8-f90e-4f86-81f5-27bc727ecad7
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: READ_PORT_BUFFER_ULONG, READ_PORT_BUFFER_ULONG routine [Kernel-Mode Driver Architecture], k103_ccd1ed9a-a7f9-4ea4-abc4-44ff756ea274.xml, kernel.read_port_buffer_ulong, wdm/READ_PORT_BUFFER_ULONG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
-	READ_PORT_BUFFER_ULONG
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---


# READ_PORT_BUFFER_ULONG function
The <b>READ_PORT_BUFFER_ULONG</b> routine reads a number of ULONG values from the specified port address into a buffer.

## Syntax

```
void READ_PORT_BUFFER_ULONG(
  PULONG Port,
  PULONG Buffer,
  ULONG  Count
);
```

## Parameters

`Port`

Specifies the port address, which must be a mapped memory range in I/O space.

`Buffer`

Pointer to a buffer into which an array of ULONG values is read.

`Count`

Specifies the number of ULONG values to be read into the buffer.


## Return Value

None

## Remarks

The size of the buffer must be large enough to contain at least the specified number of ULONG values.

Callers of <b>READ_PORT_BUFFER_ULONG</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Port</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h) |
| **Library** | Hal.lib |
| **IRQL** | Any level (see Remarks section) |