---
UID : NF:wdfhwaccess.WDF_READ_REGISTER_BUFFER_UCHAR
title : WDF_READ_REGISTER_BUFFER_UCHAR function
author : windows-driver-content
description : The WDF_READ_REGISTER_BUFFER_UCHAR function reads a number of bytes from the specified register address into a buffer.
old-location : wdf\wdf_read_register_buffer_uchar.htm
old-project : wdf
ms.assetid : D4A7F80C-C223-4F92-AD08-C37F0668B292
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdf_read_register_buffer_uchar, WDF_READ_REGISTER_BUFFER_UCHAR, wdfhwaccess/WDF_READ_REGISTER_BUFFER_UCHAR, WDF_READ_REGISTER_BUFFER_UCHAR function
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfhwaccess.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product : Windows 10 or later.
---


# WDF_READ_REGISTER_BUFFER_UCHAR function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_REGISTER_BUFFER_UCHAR</b> function reads a number of bytes from the specified register address into a buffer.

## Syntax

````
void WDF_READ_REGISTER_BUFFER_UCHAR(
  _In_  WDFDEVICE Device,
  _In_  PUCHAR    Register,
  _Out_ PUCHAR    Buffer,
  _In_  ULONG     Count 
);
````

## Parameters

`Device`

A handle to a framework device object.

`Register`

Pointer to the register, which must be a mapped range in memory space.

`Buffer`

A pointer to a buffer into which an array of UCHAR values is read.

`Count`

Specifies the number of bytes to be read into the buffer.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfhwaccess.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |