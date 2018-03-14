---
UID: NF:wdfusb.WdfUsbTargetPipeGetType
title: WdfUsbTargetPipeGetType function
author: windows-driver-content
description: The WdfUsbTargetPipeGetType method returns the type of a specified USB pipe.
old-location: wdf\wdfusbtargetpipegettype.htm
old-project: wdf
ms.assetid: d02af0c8-f963-4bec-a8b6-fe334fd75a68
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_de8bc76f-0be3-46bb-a959-b3115e91b472.xml, WdfUsbTargetPipeGetType, WdfUsbTargetPipeGetType method, kmdf.wdfusbtargetpipegettype, wdf.wdfusbtargetpipegettype, wdfusb/WdfUsbTargetPipeGetType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfUsbTargetPipeGetType
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfUsbTargetPipeGetType function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeGetType</b> method returns the type of a specified USB pipe.

## Syntax

````
WDF_USB_PIPE_TYPE WdfUsbTargetPipeGetType(
  _In_ WDFUSBPIPE Pipe
);
````

## Parameters

`Pipe`

A handle to a framework pipe object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>.


## Return Value

<b>WdfUsbTargetPipeGetType</b> returns a <a href="..\wdfusb\ne-wdfusb-_wdf_usb_pipe_type.md">WDF_USB_PIPE_TYPE</a>-typed value that identifies the specified pipe's type. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about the <b>WdfUsbTargetPipeGetType</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example determines the type of a USB pipe.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_PIPE_TYPEusbPipeType;

usbPipeType = WdfUsbTargetPipeGetType(usbPipe);
 </pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="..\wdfusb\ne-wdfusb-_wdf_usb_pipe_type.md">WDF_USB_PIPE_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetPipeGetType method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>