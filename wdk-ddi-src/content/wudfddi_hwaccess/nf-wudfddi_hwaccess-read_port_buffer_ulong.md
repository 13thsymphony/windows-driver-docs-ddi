---
UID: NF:wudfddi_hwaccess.READ_PORT_BUFFER_ULONG
title: READ_PORT_BUFFER_ULONG function
author: windows-driver-content
description: The READ_PORT_BUFFER_ULONG function reads a number of ULONG values from the specified port address into a buffer.
old-location: wdf\read_port_buffer_ulong.htm
old-project: wdf
ms.assetid: 5E1FFE55-49EE-4D8B-8826-023C751C7520
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: READ_PORT_BUFFER_ULONG, READ_PORT_BUFFER_ULONG function, umdf.read_port_buffer_ulong, wdf.read_port_buffer_ulong, wudfddi_hwaccess/READ_PORT_BUFFER_ULONG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi_hwaccess.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
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
-	Wudfddi_hwaccess.h
api_name:
-	READ_PORT_BUFFER_ULONG
product: Windows
targetos: Windows
req.typenames: UMDF_IO_TARGET_OPEN_PARAMS, *PUMDF_IO_TARGET_OPEN_PARAMS
req.product: Windows 10 or later.
---


# READ_PORT_BUFFER_ULONG function
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>READ_PORT_BUFFER_ULONG</b> function reads a number of ULONG values from the specified port address into a buffer.

## Syntax

````
void READ_PORT_BUFFER_ULONG(
  _In_  IWDFDevice3 *pDevice,
  _In_  PULONG      Port,
  _Out_ PULONG      Buffer,
  _In_  ULONG       Count 
);
````

## Parameters

`pDevice`

Specifies a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a> interface for the device object of the device to access.

`Port`

Specifies the port address, which must be a mapped memory range in I/O space.

`Buffer`

A pointer to a buffer into which an array of ULONG values is read.

`Count`

Specifies the number of ULONG values to be read into the buffer.


## Return Value

This function does not return a value.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/A0640E60-B0DF-4CAD-B292-CC1875EF7F7D">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi_hwaccess.h |
| **Library** | NtosKrnl.exe |