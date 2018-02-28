---
UID: NC:nfccx.EVT_NFC_CX_DEVICE_IO_CONTROL
title: EVT_NFC_CX_DEVICE_IO_CONTROL
author: windows-driver-content
description: Called by the NFC CX to send an unhandled IOCTL to the client driver.
old-location: nfpdrivers\evtnfccxdeviceiocontrol_.htm
old-project: nfpdrivers
ms.assetid: 45512F88-D4B8-4488-99EB-B47EE7443425
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: EVT_NFC_CX_DEVICE_IO_CONTROL, EvtNfcCxDeviceIoControl, EvtNfcCxDeviceIoControl callback function [Near-Field Proximity Drivers], nfccx/EvtNfcCxDeviceIoControl, nfpdrivers.evtnfccxdeviceiocontrol_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Requires same
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	nfccx.h
api_name:
-	EvtNfcCxDeviceIoControl
product: Windows
targetos: Windows
req.typenames: NET_PNP_EVENT, *PNET_PNP_EVENT
---


# EVT_NFC_CX_DEVICE_IO_CONTROL callback function
Called by the NFC CX to send an unhandled IOCTL to the client driver.

## Syntax

```
EVT_NFC_CX_DEVICE_IO_CONTROL EvtNfcCxDeviceIoControl;

_IRQL_requires_same_ VOID EvtNfcCxDeviceIoControl(
  WDFDEVICE Device,
  WDFREQUEST Request,
  size_t OutputBufferLength,
  size_t InputBufferLength,
  ULONG IoControlCode
)
{...}
```

## Parameters

`Device`

A handle to a framework device object.

`Request`

A handle to a framework request object.

`OutputBufferLength`

The length, in bytes, of the request's output buffer, if an output buffer is available.

`InputBufferLength`

The length, in bytes, of the request's input buffer, if an input buffer is available.

`IoControlCode`

The driver-defined or system-defined I/O control code (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">IOCTL</a>) that is associated with the request.


## Return Value

This callback function does not return a value.

## Remarks

The client can complete the request either synchronously or asynchronously. The NFC CX will complete the request if a status code other than STATUS_PENDING is returned by the client. To prevent request double completion, the client should not complete the WDFREQUEST (that is, call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>) if it returns STATUS_SUCCESS or a failure status code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 None supported |
| **Target Platform** | Desktop |
| **Header** | nfccx.h (include Ncidef.h) |
| **IRQL** | Requires same |

## See Also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20EVT_NFC_CX_DEVICE_IO_CONTROL callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>