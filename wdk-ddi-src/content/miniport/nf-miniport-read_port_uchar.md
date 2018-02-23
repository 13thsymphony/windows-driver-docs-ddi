---
UID: NF:miniport.READ_PORT_UCHAR
title: READ_PORT_UCHAR function
author: windows-driver-content
description: The READ_PORT_UCHAR routine reads a byte from the specified port address.
old-location: kernel\read_port_uchar.htm
old-project: kernel
ms.assetid: a58e55f5-d657-43bf-afef-05af7c6c02cc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k103_d0d69b7f-15ad-4a72-ad99-6a5753348f6a.xml, READ_PORT_UCHAR routine [Kernel-Mode Driver Architecture], READ_PORT_UCHAR, wdm/READ_PORT_UCHAR, kernel.read_port_uchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: miniport.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hal.lib
-	Hal.dll
apiname:
-	READ_PORT_UCHAR
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---


# READ_PORT_UCHAR function
The <b>READ_PORT_UCHAR</b> routine reads a byte from the specified port address.

## Syntax

````
UCHAR READ_PORT_UCHAR(
  _In_ PUCHAR Port
);
````

## Parameters

`Port`




## Return Value

<b>READ_PORT_UCHAR</b> returns the byte that is read from the specified port address.

## Remarks

Callers of <b>READ_PORT_UCHAR</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h) |
| **Library** | Hal.lib |
| **IRQL** | Any level (see Remarks section) |