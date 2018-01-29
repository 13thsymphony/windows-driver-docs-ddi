---
UID : NF:wdfhwaccess.WDF_READ_REGISTER_BUFFER_ULONG64
title : WDF_READ_REGISTER_BUFFER_ULONG64 function
author : windows-driver-content
description : The WDF_READ_REGISTER_BUFFER_ULONG64 function reads a number of ULONG64 values from the specified register address into a buffer.
old-location : wdf\wdf_read_register_buffer_ulong64.htm
old-project : wdf
ms.assetid : E06F6BE4-C450-4810-BB7A-B2818C76A818
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdfhwaccess/WDF_READ_REGISTER_BUFFER_ULONG64, wdf.wdf_read_register_buffer_ulong64, WDF_READ_REGISTER_BUFFER_ULONG64 function, WDF_READ_REGISTER_BUFFER_ULONG64
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
req.typenames : "*PWDF_FILE_INFORMATION_CLASS, WDF_FILE_INFORMATION_CLASS"
req.product : Windows 10 or later.
---


# WDF_READ_REGISTER_BUFFER_ULONG64 function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_REGISTER_BUFFER_ULONG64</b> function reads a number of ULONG64 values from the specified register address into a buffer.

## Syntax

````
void WDF_READ_REGISTER_BUFFER_ULONG64(
  _In_  WDFDEVICE Device,
  _In_  PULONG64  Register,
  _Out_ PULONG64  Buffer,
  _In_  ULONG     Count 
);
````

## Parameters

`Device`

A handle to a framework device object.

`Register`

A pointer to the register, which must be a mapped range in memory space.

`Buffer`

A pointer to a buffer into which an array of ULONG64 values is read.

`Count`

Specifies the number of ULONG64 values to be read into the buffer.


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