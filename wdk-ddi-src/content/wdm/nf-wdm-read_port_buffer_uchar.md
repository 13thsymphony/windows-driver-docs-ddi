---
UID: NF:wdm.READ_PORT_BUFFER_UCHAR
title: READ_PORT_BUFFER_UCHAR function
author: windows-driver-content
description: The READ_PORT_BUFFER_UCHAR routine reads a number of bytes from the specified port address into a buffer.
old-location: kernel\read_port_buffer_uchar.htm
old-project: kernel
ms.assetid: a32a7c6a-16dd-4d12-aa32-6bdb60990568
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: READ_PORT_BUFFER_UCHAR routine [Kernel-Mode Driver Architecture], k103_020afa73-5210-42d8-a2a5-dc9ac663af2c.xml, READ_PORT_BUFFER_UCHAR, wdm/READ_PORT_BUFFER_UCHAR, kernel.read_port_buffer_uchar
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
-	READ_PORT_BUFFER_UCHAR
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# READ_PORT_BUFFER_UCHAR function
The <b>READ_PORT_BUFFER_UCHAR</b> routine reads a number of bytes from the specified port address into a buffer.

## Syntax

````
VOID READ_PORT_BUFFER_UCHAR(
  _In_  PUCHAR Port,
  _Out_ PUCHAR Buffer,
  _In_  ULONG  Count
);
````

## Parameters

`Port`

Specifies the port address, which must be a mapped memory range in I/O space.

`Buffer`

Pointer to a buffer into which an array of UCHAR values is read.

`Count`

Specifies the number of bytes to be read into the buffer.


## Return Value

None

## Remarks

The size of the buffer must be large enough to contain at least the specified number of bytes.

Callers of <b>READ_PORT_BUFFER_UCHAR</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Port</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | Hal.lib |
| **IRQL** | Any level (see Remarks section) |