---
UID: NF:wdfhwaccess.WDF_READ_PORT_USHORT
title: WDF_READ_PORT_USHORT function
author: windows-driver-content
description: The WDF_READ_PORT_USHORT function reads a USHORT value from the specified port address.
old-location: wdf\wdf_read_port_ushort.htm
old-project: wdf
ms.assetid: F9688E1F-D8A3-432E-8724-2D601946E707
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_READ_PORT_USHORT, wdfhwaccess/WDF_READ_PORT_USHORT, WDF_READ_PORT_USHORT function, wdf.wdf_read_port_ushort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfhwaccess.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdfhwaccess.h
apiname:
-	WDF_READ_PORT_USHORT
product: Windows
targetos: Windows
req.typenames: "*PWDF_FILE_INFORMATION_CLASS, WDF_FILE_INFORMATION_CLASS"
req.product: Windows 10 or later.
---


# WDF_READ_PORT_USHORT function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_PORT_USHORT</b>  function reads a USHORT value from the specified port address.

## Syntax

````
USHORT WDF_READ_PORT_USHORT(
  _In_ WDFDEVICE Device,
  _In_ PUSHORT   Port
);
````

## Parameters

`Device`

A handle to a framework device object.

`Port`

Specifies the port address, which must be a mapped memory range in I/O space.


## Return Value

<b>WDF_READ_PORT_USHORT</b> returns the USHORT value that is read from the specified port address.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1  |
| **Target Platform** | Universal |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfhwaccess.h |
| **Library** | NtosKrnl.exe |