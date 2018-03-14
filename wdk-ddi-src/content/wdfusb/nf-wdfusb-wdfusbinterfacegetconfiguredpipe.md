---
UID: NF:wdfusb.WdfUsbInterfaceGetConfiguredPipe
title: WdfUsbInterfaceGetConfiguredPipe function
author: windows-driver-content
description: The WdfUsbInterfaceGetConfiguredPipe method returns a handle to the framework pipe object that is associated with a specified USB device interface and pipe index. Optionally, the method also returns information about the pipe.
old-location: wdf\wdfusbinterfacegetconfiguredpipe.htm
old-project: wdf
ms.assetid: 0836a969-e484-485f-9b65-202c177b4f43
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_65a97d99-39c5-4750-95e1-6c9c20c169bb.xml, WdfUsbInterfaceGetConfiguredPipe, WdfUsbInterfaceGetConfiguredPipe method, kmdf.wdfusbinterfacegetconfiguredpipe, wdf.wdfusbinterfacegetconfiguredpipe, wdfusb/WdfUsbInterfaceGetConfiguredPipe
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
-	WdfUsbInterfaceGetConfiguredPipe
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfUsbInterfaceGetConfiguredPipe function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbInterfaceGetConfiguredPipe</b> method returns a handle to the framework pipe object that is associated with a specified USB device interface and pipe index. Optionally, the method also returns information about the pipe.

## Syntax

````
WDFUSBPIPE WdfUsbInterfaceGetConfiguredPipe(
  _In_      WDFUSBINTERFACE           UsbInterface,
  _In_      UCHAR                     PipeIndex,
  _Out_opt_ PWDF_USB_PIPE_INFORMATION PipeInfo
);
````

## Parameters

`UsbInterface`

A handle to a USB interface object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>.

`PipeIndex`

A zero-based index into the set of framework pipe objects that are associated with the specified interface object.

`PipeInfo`

A pointer to a caller-allocated <a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a> structure that the framework fills in. This parameter is optional and can be <b>NULL</b>.


## Return Value

If the operation succeeds, <b>WdfUsbInterfaceGetConfiguredPipe</b> returns a handle to the framework pipe object that is associated with the specified interface object and pipe index. The method returns <b>NULL</b> if the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a> structure's size is incorrect or if the pipe index value is too large.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Your driver can call <b>WdfUsbInterfaceGetConfiguredPipe</b> after it has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>.

For more information about the <b>WdfUsbInterfaceGetConfiguredPipe</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example sends a USB abort request to each configured pipe of a specified USB interface.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BYTE  count, i;
NTSTATUS  status;

count = WdfUsbInterfaceGetNumConfiguredPipes(UsbInterface);

for (i = 0; i &lt; count; i++) {
    WDFUSBPIPE pipe;
    pipe = WdfUsbInterfaceGetConfiguredPipe(
                                            UsbInterface,
                                            i,
                                            NULL
                                            );
    status = WdfUsbTargetPipeAbortSynchronously(
                                            pipe,
                                            WDF_NO_HANDLE,
                                            NULL
                                            );

    if (!NT_SUCCESS(status)) {
        break;
    }
}</pre>
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

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetinterface.md">WdfUsbTargetDeviceGetInterface</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetnumconfiguredpipes.md">WdfUsbInterfaceGetNumConfiguredPipes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbInterfaceGetConfiguredPipe method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>