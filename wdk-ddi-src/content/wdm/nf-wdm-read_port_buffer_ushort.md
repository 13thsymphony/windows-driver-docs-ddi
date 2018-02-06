---
UID: NF:wdm.READ_PORT_BUFFER_USHORT
title: READ_PORT_BUFFER_USHORT function
author: windows-driver-content
description: The READ_PORT_BUFFER_USHORT routine reads a number of USHORT values from the specified port address into a buffer.
old-location: kernel\read_port_buffer_ushort.htm
old-project: kernel
ms.assetid: 27c2f249-bfd2-497d-aa34-f5d1e1a1fac7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: READ_PORT_BUFFER_USHORT, wdm/READ_PORT_BUFFER_USHORT, k103_59466909-4881-4b5f-95aa-c1d742ef17af.xml, READ_PORT_BUFFER_USHORT routine [Kernel-Mode Driver Architecture], kernel.read_port_buffer_ushort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hal.lib
-	Hal.dll
apiname:
-	READ_PORT_BUFFER_USHORT
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# READ_PORT_BUFFER_USHORT function
The <b>READ_PORT_BUFFER_USHORT</b> routine reads a number of USHORT values from the specified port address into a buffer.

## Syntax

````
VOID READ_PORT_BUFFER_USHORT(
  _In_  PUSHORT Port,
  _Out_ PUSHORT Buffer,
  _In_  ULONG   Count
);
````

## Parameters

`Port`

Specifies the port address, which must be a mapped memory range in I/O space.

`Buffer`

Pointer to a buffer into which an array of USHORT values is read.

`Count`

Specifies the number of USHORT values to be read into the buffer.


## Return Value

None

## Remarks

The size of the buffer must be large enough to contain at least the specified number of USHORT values.

Callers of <b>READ_PORT_BUFFER_USHORT</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Port</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | Hal.lib |
| **IRQL** | Any level (see Remarks section) |