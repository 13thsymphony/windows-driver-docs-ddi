---
UID : NF:ufxclient.UfxDeviceIoControl
title : UfxDeviceIoControl function
author : windows-driver-content
description : Passes non-internal IOCTLs from user-mode to UFX.
old-location : buses\ufxdeviceiocontrol.htm
old-project : usbref
ms.assetid : 18D4C334-1AD9-4CBF-8BF1-063A8E837A21
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : UfxDeviceIoControl
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ufxclient.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : UfxDeviceIoControl
req.alt-loc : ufxclient.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : DISPATCH_LEVEL
req.typenames : UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product : Windows 10 or later.
---


# UfxDeviceIoControl function
Passes non-internal IOCTLs from user-mode to UFX.

## Syntax

````
BOOLEAN UfxDeviceIoControl(
  [in] UFXDEVICE  UfxDevice,
  [in] WDFREQUEST Request,
  [in] size_t     OutputBufferLength,
  [in] size_t     InputBufferLength,
  [in] ULONG      IoControlCode
);
````

## Parameters

`UfxDevice`

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.

`Request`

A handle to a framework request object.

`OutputBufferLength`

The length, in bytes, of the request's output buffer, if an output buffer is available.

`InputBufferLength`

The length, in bytes, of the request's input buffer, if an input buffer is available.

`IoControlCode`

The driver-defined or system-defined IOCTL that is associated with the request.


## Return Value

None

## Remarks

The client driver calls <b>UfxDeviceIoControl</b> to forward non-internal IOCTLs that it receives in its <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_device_control.md">EvtIoDeviceControl</a> callback function to UFX.  The following example shows how:</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ufxclient.h |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** |  |