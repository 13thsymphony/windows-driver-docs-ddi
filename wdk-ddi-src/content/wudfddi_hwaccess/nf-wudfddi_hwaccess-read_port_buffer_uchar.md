---
UID : NF:wudfddi_hwaccess.READ_PORT_BUFFER_UCHAR
title : READ_PORT_BUFFER_UCHAR function
author : windows-driver-content
description : The READ_PORT_BUFFER_UCHAR function reads a number of bytes from the specified port address into a buffer.
old-location : wdf\read_port_buffer_uchar.htm
old-project : wdf
ms.assetid : CDA0A86B-94E7-4825-9826-0E12ECF42B57
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : READ_PORT_BUFFER_UCHAR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wudfddi_hwaccess.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.11
req.alt-api : READ_PORT_BUFFER_UCHAR
req.alt-loc : Wudfddi_hwaccess.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PUMDF_IO_TARGET_OPEN_PARAMS, UMDF_IO_TARGET_OPEN_PARAMS"
req.product : Windows 10 or later.
---


# READ_PORT_BUFFER_UCHAR function
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>READ_PORT_BUFFER_UCHAR</b> function reads a number of bytes from the specified port address into a buffer.

## Syntax

````
void READ_PORT_BUFFER_UCHAR(
  _In_  IWDFDevice3 *pDevice,
  _In_  PUCHAR      Port,
  _Out_ PUCHAR      Buffer,
  _In_  ULONG       Count 
);
````

## Parameters

`pDevice`

Specifies a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a> interface for the device object of the device to access.

`Port`

Specifies the port address, which must be a mapped memory range in I/O space.

`Buffer`

A pointer to a buffer into which an array of UCHAR values is read.

`Count`

Specifies the number of bytes to be read into the buffer.


## Return Value

This function does not return a value.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/A0640E60-B0DF-4CAD-B292-CC1875EF7F7D">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi_hwaccess.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |