---
UID: NF:wdfhwaccess.WDF_WRITE_REGISTER_BUFFER_ULONG
title: WDF_WRITE_REGISTER_BUFFER_ULONG function
author: windows-driver-content
description: The WDF_WRITE_REGISTER_BUFFER_ULONG function writes a number of ULONG values from a buffer to the specified register.
old-location: wdf\wdf_write_register_buffer_ulong.htm
old-project: wdf
ms.assetid: D52888A2-4CC1-4C5A-890E-5585424339E0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_WRITE_REGISTER_BUFFER_ULONG, WDF_WRITE_REGISTER_BUFFER_ULONG function, wdf.wdf_write_register_buffer_ulong, wdfhwaccess/WDF_WRITE_REGISTER_BUFFER_ULONG
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
req.lib: 
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
-	WDF_WRITE_REGISTER_BUFFER_ULONG
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---


# WDF_WRITE_REGISTER_BUFFER_ULONG function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_WRITE_REGISTER_BUFFER_ULONG</b> function writes a number of ULONG values from a buffer to the specified register.

## Syntax

```
void WDF_WRITE_REGISTER_BUFFER_ULONG(
  WDFDEVICE Device,
  PULONG    Register,
  PULONG    Buffer,
  ULONG     Count
);
```

## Parameters

`Device`

A handle to a framework device object.

`Register`

A pointer to the register, which must be a mapped range in memory space.

`Buffer`

A pointer to a buffer from which an array of ULONG values is to be written.

`Count`

Specifies the number of ULONG values to write to the register.


## Return Value

This function does not return a value.

## Remarks

The size of the buffer must be large enough to contain at least the specified number of bytes.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1  |
| **Target Platform** | Universal |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfhwaccess.h |