---
UID: NF:wdfusb.WdfUsbTargetDeviceQueryString
title: WdfUsbTargetDeviceQueryString function
author: windows-driver-content
description: The WdfUsbTargetDeviceQueryString method retrieves the Unicode string that is associated with a specified USB device and descriptor index value.
old-location: wdf\wdfusbtargetdevicequerystring.htm
old-project: wdf
ms.assetid: e7b25a47-e197-4670-9907-409d5aeb5462
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFUSBTARGETDEVICEQUERYSTRING, kmdf.wdfusbtargetdevicequerystring, WdfUsbTargetDeviceQueryString, wdfusb/WdfUsbTargetDeviceQueryString, DFUsbRef_ea603209-6043-48e6-b8ff-4795f572dea6.xml, wdf.wdfusbtargetdevicequerystring, WdfUsbTargetDeviceQueryString method
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfUsbTargetDeviceQueryString
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfUsbTargetDeviceQueryString function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceQueryString</b> method retrieves the Unicode string that is associated with a specified USB device and descriptor index value.

## Syntax

````
NTSTATUS WdfUsbTargetDeviceQueryString(
  _In_      WDFUSBDEVICE              UsbDevice,
  _In_opt_  WDFREQUEST                Request,
  _In_opt_  PWDF_REQUEST_SEND_OPTIONS RequestOptions,
  _Out_opt_ PUSHORT                   String,
  _Inout_   PUSHORT                   NumCharacters,
  _In_      UCHAR                     StringIndex,
  _In_opt_  USHORT                    LangID
);
````

## Parameters

`UsbDevice`

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.

`Request`

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

`RequestOptions`

A pointer to a caller-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

`String`

A pointer to a caller-allocated buffer that receives the requested Unicode string. The string is NULL-terminated only if the device supplies a NULL-terminated string. If this pointer is <b>NULL</b>, <b>WdfUsbTargetDeviceQueryString</b> returns the required buffer size (that is, the required number of Unicode characters) in the location that <i>NumCharacters</i> points to.

`NumCharacters`

A pointer to a caller-allocated variable. The caller supplies the number of Unicode characters that the buffer can hold. When <b>WdfUsbTargetDeviceQueryString</b> returns, the variable receives the number of characters (including the NULL terminator, if supplied) that are in the Unicode string that the <i>String</i> buffer receives.

`StringIndex`

An index value that identifies the Unicode string. This index value is obtained from a <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>, <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>, or <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure.

`LangID`

A language identifier. The Unicode string will be retrieved for the language that this identifier specifies. For information about obtaining a device's supported language identifiers, see the USB specification.


## Return Value

<b>WdfUsbTargetDeviceQueryString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:
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
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A memory buffer could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_DATA_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The USB device returned an invalid descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The supplied buffer was too small.

</td>
</tr>
</table> 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Drivers should call <b>WdfUsbTargetDeviceQueryString</b> twice, by using the following steps:
<ul>
<li>
Set the <i>String</i> pointer to <b>NULL</b>, so that <b>WdfUsbTargetDeviceQueryString</b> will return the required buffer size in the address that the <i>NumCharacters</i> parameter points to.

</li>
<li>
 Allocate buffer space to hold the number of Unicode characters that are in the requested string. For example, a driver might call <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> to allocate a buffer, or it might call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> to create a framework memory object.

</li>
<li>
Call <b>WdfUsbTargetDeviceQueryString</b> again, setting the <i>String</i> value to a pointer to the new buffer and setting <i>NumCharacters</i> to the buffer's length (that is, the number of Unicode characters, not the byte length).

</li>
</ul><b>WdfUsbTargetDeviceQueryString</b> locates the specified USB string descriptor and copies the Unicode string from the descriptor into the supplied buffer. 

If your driver specifies a non-<b>NULL</b> value for the <i>Request</i> parameter, the framework uses the specified request object, and another driver thread can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a>, if necessary, to attempt to cancel the string query request. If the driver specifies a <b>NULL</b> value for <i>Request</i>, the framework uses an internal request object that the driver cannot cancel. 

Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

For more information about USB string descriptors, see the USB specification.

For more information about the <b>WdfUsbTargetDeviceQueryString</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a>

<a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>

<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceallocandquerystring.md">WdfUsbTargetDeviceAllocAndQueryString</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceQueryString method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>