---
UID: NF:miniport.WRITE_PORT_UCHAR
title: WRITE_PORT_UCHAR function
author: windows-driver-content
description: The WRITE_PORT_UCHAR routine writes a byte to the specified port address.
old-location: kernel\write_port_uchar.htm
old-project: kernel
ms.assetid: 951b688f-21fa-4555-b877-e140e46a1700
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/WRITE_PORT_UCHAR, kernel.write_port_uchar, WRITE_PORT_UCHAR routine [Kernel-Mode Driver Architecture], k103_1495098b-03fb-4677-ac5a-2a1de9223f8b.xml, WRITE_PORT_UCHAR
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
-	WRITE_PORT_UCHAR
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---


# WRITE_PORT_UCHAR function
The <b>WRITE_PORT_UCHAR</b> routine writes a byte to the specified port address.

## Syntax

````
 VOID WRITE_PORT_UCHAR(
  _In_ PUCHAR Port,
  _In_ UCHAR  Value
);
````

## Parameters

`Port`



`Value`




## Return Value

None

## Remarks

Callers of <b>WRITE_PORT_UCHAR</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h) |
| **Library** | Hal.lib |
| **IRQL** | Any level (see Remarks section) |