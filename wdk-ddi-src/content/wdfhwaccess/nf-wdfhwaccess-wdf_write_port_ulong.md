---
UID: NF:wdfhwaccess.WDF_WRITE_PORT_ULONG
title: WDF_WRITE_PORT_ULONG function
author: windows-driver-content
description: The WDF_WRITE_PORT_ULONG function writes a ULONG value to the specified port address.
old-location: wdf\wdf_write_port_ulong.htm
old-project: wdf
ms.assetid: 553CA9E0-66C7-436B-AE34-5A6201479D6D
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WDF_WRITE_PORT_ULONG, WDF_WRITE_PORT_ULONG function, wdf.wdf_write_port_ulong, wdfhwaccess/WDF_WRITE_PORT_ULONG
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdfhwaccess.h
api_name:
-	WDF_WRITE_PORT_ULONG
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---


# WDF_WRITE_PORT_ULONG function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_WRITE_PORT_ULONG</b> function writes a ULONG value to the specified port address.

## Syntax

````
void WDF_WRITE_PORT_ULONG(
  _In_ WDFDEVICE Device,
  _In_ PULONG    Port,
  _In_ ULONG     Value
);
````

## Parameters

`Device`

A handle to a framework device object.

`Port`

A pointer to the port, which must be a mapped memory range in I/O space.

`Value`

Specifies a ULONG value to be written to the port.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1  |
| **Target Platform** | Universal |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfhwaccess.h |
| **Library** | NtosKrnl.exe |