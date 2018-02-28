---
UID: NF:wdfusb.WdfUsbTargetDeviceFormatRequestForString
title: WdfUsbTargetDeviceFormatRequestForString function
author: windows-driver-content
description: The WdfUsbTargetDeviceFormatRequestForString method builds a request for the USB string descriptor that is associated with a USB device's string index value.
old-location: wdf\wdfusbtargetdeviceformatrequestforstring.htm
old-project: wdf
ms.assetid: f1875578-33c1-4d9e-865b-f1f5391f4aca
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFUsbRef_ff5bebaa-3db1-4f9a-bac4-2e5e5c297d03.xml, WdfUsbTargetDeviceFormatRequestForString, WdfUsbTargetDeviceFormatRequestForString method, kmdf.wdfusbtargetdeviceformatrequestforstring, wdf.wdfusbtargetdeviceformatrequestforstring, wdfusb/WdfUsbTargetDeviceFormatRequestForString
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestForUrbXrb, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2, UsbKmdfIrql, UsbKmdfIrql2
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
-	WdfUsbTargetDeviceFormatRequestForString
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfUsbTargetDeviceFormatRequestForString function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceFormatRequestForString</b> method builds a request for the USB string descriptor that is associated with a USB device's string index value.

## Syntax

````
NTSTATUS WdfUsbTargetDeviceFormatRequestForString(
  _In_     WDFUSBDEVICE      UsbDevice,
  _In_     WDFREQUEST        Request,
  _In_     WDFMEMORY         Memory,
  _In_opt_ PWDFMEMORY_OFFSET Offset,
  _In_     UCHAR             StringIndex,
  _In_opt_ USHORT            LangID
);
````

## Parameters

`UsbDevice`

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.

`Request`

A handle to a framework request object.

`Memory`

A handle to a framework memory object.

`Offset`

A pointer to a caller-allocated <a href="..\wdfmemory\ns-wdfmemory-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the output buffer, for storing the string descriptor. If this pointer is <b>NULL</b>, the descriptor is stored at the beginning of the output buffer, and the maximum string length is the buffer length.

`StringIndex`

An index value that identifies the string. This index value is obtained from a <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>, <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>, or <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure.

`LangID`

A language identifier. The string will be retrieved for the language that this identifier specifies. For information about obtaining a device's supported language identifiers, see the USB specification.


## Return Value

<b>WdfUsbTargetDeviceFormatRequestForString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The buffer's byte count was not an even number.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The offset that <i>Offset</i> specifies was invalid.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

After <b>WdfUsbTargetDeviceFormatRequestForString</b> returns, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> to send the request. After <b>WdfRequestSend</b> returns, the driver can pass the <i>Memory</i> handle to <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a> to obtain a pointer to the memory buffer. The buffer will contain a <a href="..\usbspec\ns-usbspec-_usb_string_descriptor.md">USB_STRING_DESCRIPTOR</a> structure that describes the string descriptor.

For more information about the <b>WdfUsbTargetDeviceFormatRequestForString</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example creates a request object and a memory object, and it passes the object handles to <b>WdfUsbTargetDeviceFormatRequestForString</b>. Then, the example sets a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function for the request and sends the request to an I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS status;
PDEVICE_CONTEXT  deviceContext = GetDeviceContext(device);
WDFREQUEST  request;
WDFMEMORY  memHandle;
WDF_OBJECT_ATTRIBUTES  attributes;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);

status = WdfRequestCreate(
                          &amp;attributes,
                          WdfUsbTargetDeviceGetIoTarget(deviceContext-&gt;UsbTargetDevice),
                          &amp;request
                          );

if (!NT_SUCCESS(status)){
    return status;
}
status = WdfMemoryCreate(
                         WDF_NO_OBJECT_ATTRIBUTES,
                         NonPagedPool,
                         0,
                         STR_DESC_STRING_SIZE,
                         &amp;memHandle,
                         NULL
                         );
if (!NT_SUCCESS(status)){
    WdfObjectDelete(request);
    return status;
}
status = WdfUsbTargetDeviceFormatRequestForString(
                         deviceContext-&gt;UsbTargetDevice,
                         request,
                         memHandle,
                         NULL,
                         deviceContext-&gt;UsbDeviceDescr.iManufacturer,
                         0x0409
                         );
if (NT_SUCCESS(status)) {
    WdfRequestSetCompletionRoutine(
                                   request,
                                   MyCompletionRoutine,
                                   NULL
                                   );

    if (WdfRequestSend(
                       request,
                       WdfUsbTargetDeviceGetIoTarget(deviceContext-&gt;UsbTargetDevice),
                       NULL
                       )) {
        status = STATUS_PENDING;
    }
}
else {
    WdfObjectDelete(memHandle);
    WdfObjectDelete(request);
    return status;
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
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestForUrbXrb, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceallocandquerystring.md">WdfUsbTargetDeviceAllocAndQueryString</a>



<a href="..\usbspec\ns-usbspec-_usb_string_descriptor.md">USB_STRING_DESCRIPTOR</a>



<a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetcompletionroutine.md">WdfRequestSetCompletionRoutine</a>



<a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>



<a href="..\wdfmemory\ns-wdfmemory-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>

<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>



<a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceFormatRequestForString method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>