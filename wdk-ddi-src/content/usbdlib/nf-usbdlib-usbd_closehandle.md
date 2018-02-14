---
UID: NF:usbdlib.USBD_CloseHandle
title: USBD_CloseHandle function
author: windows-driver-content
description: The USBD_CloseHandle routine is called by a USB client driver to close a USBD handle and release all resources associated with the driver's registration.
old-location: buses\usbd_unregister.htm
old-project: usbref
ms.assetid: 6876E96D-E249-4B7C-A496-27E3F4A7F7E2
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.usbd_unregister, usbdlib/USBD_CloseHandle, USBD_CloseHandle routine [Buses], USBD_CloseHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires DDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbdex.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Usbdex.lib
-	Usbdex.dll
apiname:
-	USBD_CloseHandle
product: Windows
targetos: Windows
req.typenames: "*PUSBCAMD_DEVICE_DATA2, USBCAMD_DEVICE_DATA2"
req.product: Windows 10 or later.
---


# USBD_CloseHandle function
The  <b>USBD_CloseHandle</b> routine is called by a USB client driver to close a USBD handle and release all resources associated with the driver's registration.

## Syntax

````
VOID USBD_CloseHandle(
  _In_ USBD_HANDLE USBDHandle
);
````

## Parameters

`USBDHandle`

USBD handle to be closed. The handle is retrieved by the client driver in a previous call to  the <a href="..\usbdlib\nf-usbdlib-usbd_createhandle.md">USBD_CreateHandle</a> routine.


## Return Value

This routine does not return a value.

## Remarks

A client driver should call <b>USBD_CloseHandle</b> in the driver's routine that handles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> IRP. The client driver must call the routine before sending the IRP down the USB driver stack.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Requires DDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system. Requires DDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system. |
| **Target Platform** | Desktop |
| **Header** | usbdlib.h |
| **Library** | Usbdex.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\usbdlib\nf-usbdlib-usbd_createhandle.md">USBD_CreateHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450844">Allocating and Building URBs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_CloseHandle routine%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>