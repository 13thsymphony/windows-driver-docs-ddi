---
UID: NF:usbdlib.USBD_CloseHandle
title: USBD_CloseHandle function
author: windows-driver-content
description: The USBD_CloseHandle routine is called by a USB client driver to close a USBD handle and release all resources associated with the driver's registration.
old-location: buses\usbd_unregister.htm
old-project: usbref
ms.assetid: 6876E96D-E249-4B7C-A496-27E3F4A7F7E2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: USBD_CloseHandle
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
req.alt-api: USBD_CloseHandle
req.alt-loc: Usbdex.lib,Usbdex.dll
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
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_CloseHandle function



## -description
The  <b>USBD_CloseHandle</b> routine is called by a USB client driver to close a USBD handle and release all resources associated with the driver's registration.



## -syntax

````
VOID USBD_CloseHandle(
  _In_ USBD_HANDLE USBDHandle
);
````


## -parameters

### -param USBDHandle [in]

USBD handle to be closed. The handle is retrieved by the client driver in a previous call to  the <a href="..\usbdlib\nf-usbdlib-usbd_createhandle.md">USBD_CreateHandle</a> routine.


## -returns
This routine does not return a value.


## -remarks
A client driver should call <b>USBD_CloseHandle</b> in the driver's routine that handles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> IRP. The client driver must call the routine before sending the IRP down the USB driver stack. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Requires DDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbdlib.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Usbdex.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usbdlib\nf-usbdlib-usbd_createhandle.md">USBD_CreateHandle</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450844">Allocating and Building URBs</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_CloseHandle routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

