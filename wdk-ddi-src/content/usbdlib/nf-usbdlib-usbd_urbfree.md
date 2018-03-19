---
UID: NF:usbdlib.USBD_UrbFree
title: USBD_UrbFree function
author: windows-driver-content
description: The USBD_UrbFree routine releases the URB that is allocated by USBD_UrbAllocate, USBD_IsochUrbAllocate, USBD_SelectConfigUrbAllocateAndBuild, or USBD_SelectInterfaceUrbAllocateAndBuild.
old-location: buses\usbd_urbfree.htm
old-project: usbref
ms.assetid: DD80BAA0-EC01-4231-827A-962580D1E201
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: USBD_UrbFree, USBD_UrbFree routine [Buses], buses.usbd_urbfree, usbdlib/USBD_UrbFree
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbdex.lib
-	Usbdex.dll
api_name:
-	USBD_UrbFree
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---


# USBD_UrbFree function
The <b>USBD_UrbFree</b> routine releases the <a href="..\usb\ns-usb-_urb.md">URB</a> that is allocated by <a href="..\usbdlib\nf-usbdlib-usbd_urballocate.md">USBD_UrbAllocate</a>, <a href="..\usbdlib\nf-usbdlib-usbd_isochurballocate.md">USBD_IsochUrbAllocate</a>, <a href="..\usbdlib\nf-usbdlib-usbd_selectconfigurballocateandbuild.md">USBD_SelectConfigUrbAllocateAndBuild</a>, or 
    <a href="..\usbdlib\nf-usbdlib-usbd_selectinterfaceurballocateandbuild.md">USBD_SelectInterfaceUrbAllocateAndBuild</a>.

## Syntax

````
void USBD_UrbFree(
  _In_ USBD_HANDLE USBDHandle,
  _In_ PURB        Urb
);
````

## Parameters

`USBDHandle`

USBD handle that is retrieved by the client driver in a previous call to  the <a href="..\usbdlib\nf-usbdlib-usbd_createhandle.md">USBD_CreateHandle</a> routine.

`Urb`

Pointer to the <a href="..\usb\ns-usb-_urb.md">URB</a> structure to be released.


## Return Value

This routine does not return a value.

## Remarks

You must call <b>USBD_UrbFree</b> to release the URB allocated by <a href="..\usbdlib\nf-usbdlib-usbd_urballocate.md">USBD_UrbAllocate</a> after the request is complete. 

Failure to call <b>USBD_UrbFree</b> can cause a memory leak. 

For a code example, see <a href="..\usbdlib\nf-usbdlib-usbd_urballocate.md">USBD_UrbAllocate</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.  |
| **Target Platform** | Desktop |
| **Header** | usbdlib.h |
| **Library** | Usbdex.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450844">Allocating and Building URBs</a>



<a href="..\usbdlib\nf-usbdlib-usbd_urballocate.md">USBD_UrbAllocate</a>