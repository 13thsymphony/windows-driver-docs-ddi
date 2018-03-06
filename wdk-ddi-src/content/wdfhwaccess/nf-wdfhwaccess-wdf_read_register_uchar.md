---
UID: NF:wdfhwaccess.WDF_READ_REGISTER_UCHAR
title: WDF_READ_REGISTER_UCHAR function
author: windows-driver-content
description: The WDF_READ_REGISTER_UCHAR function reads a byte from the specified register address.
old-location: wdf\wdf_read_register_uchar.htm
old-project: wdf
ms.assetid: C8633689-0900-42BB-9D0D-6F95CBA13A37
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_READ_REGISTER_UCHAR, WDF_READ_REGISTER_UCHAR function, wdf.wdf_read_register_uchar, wdfhwaccess/WDF_READ_REGISTER_UCHAR
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
-	WDF_READ_REGISTER_UCHAR
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---


# WDF_READ_REGISTER_UCHAR function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_REGISTER_UCHAR</b> function reads a byte from the specified register address.

## Syntax

````
UCHAR WDF_READ_REGISTER_UCHAR(
  _In_ WDFDEVICE Device,
  _In_ PUCHAR    Register
);
````

## Parameters

`Device`

A handle to a framework device object.

`Register`

A pointer to the register address, which must be a mapped range in memory space.


## Return Value

<b>WDF_READ_REGISTER_UCHAR</b> returns the byte that is read from the specified port address.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1  |
| **Target Platform** | Universal |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfhwaccess.h |
| **Library** | NtosKrnl.exe |