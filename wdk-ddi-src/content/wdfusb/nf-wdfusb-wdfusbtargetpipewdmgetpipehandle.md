---
UID: NF:wdfusb.WdfUsbTargetPipeWdmGetPipeHandle
title: WdfUsbTargetPipeWdmGetPipeHandle function
author: windows-driver-content
description: The WdfUsbTargetPipeWdmGetPipeHandle method returns the USBD_PIPE_HANDLE-typed handle that is associated with a specified framework pipe object.
old-location: wdf\wdfusbtargetpipewdmgetpipehandle.htm
old-project: wdf
ms.assetid: d24577e3-3124-4ce7-a6ea-bed75ff18a1e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfUsbTargetPipeWdmGetPipeHandle, wdf.wdfusbtargetpipewdmgetpipehandle, DFUsbRef_4dc66ce5-f27f-4d35-bcea-0efb60a1de3c.xml, PFN_WDFUSBTARGETPIPEWDMGETPIPEHANDLE, wdfusb/WdfUsbTargetPipeWdmGetPipeHandle, kmdf.wdfusbtargetpipewdmgetpipehandle, WdfUsbTargetPipeWdmGetPipeHandle method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfUsbTargetPipeWdmGetPipeHandle
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfUsbTargetPipeWdmGetPipeHandle function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfUsbTargetPipeWdmGetPipeHandle</b> method returns the USBD_PIPE_HANDLE-typed handle that is associated with a specified framework pipe object.

## Syntax

````
USBD_PIPE_HANDLE WdfUsbTargetPipeWdmGetPipeHandle(
  _In_ WDFUSBPIPE UsbPipe
);
````

## Parameters

`UsbPipe`

A handle to a framework pipe object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>.


## Return Value

<b>WdfUsbTargetPipeWdmGetPipeHandle</b> returns a USBD_PIPE_HANDLE-typed handle. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A framework-based driver needs to obtain a USBD_PIPE_HANDLE-typed handle only if it creates a <a href="..\usb\ns-usb-_urb.md">URB</a> that requires a pipe handle.

The driver can call the <b>WdfUsbTargetPipeWdmGetPipeHandle</b> method after it has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>. The USBD_PIPE_HANDLE-typed handle that <b>WdfUsbTargetPipeWdmGetPipeHandle</b> returns is valid until the driver calls <b>WdfUsbTargetDeviceSelectConfig</b> again, the driver calls <a href="..\wdfusb\nf-wdfusb-wdfusbinterfaceselectsetting.md">WdfUsbInterfaceSelectSetting</a>, or the framework pipe object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the framework pipe object, and if the object is deleted before the driver calls <b>WdfUsbTargetDeviceSelectConfig</b> again or calls <b>WdfUsbInterfaceSelectSetting</b>, the handle is valid until the object's <i>EvtCleanupCallback</i> function returns.

For more information about the <b>WdfUsbTargetPipeWdmGetPipeHandle</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>

<a href="..\usb\ns-usb-_urb.md">URB</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetPipeWdmGetPipeHandle method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>