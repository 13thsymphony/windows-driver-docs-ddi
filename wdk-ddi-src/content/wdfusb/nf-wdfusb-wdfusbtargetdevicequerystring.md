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
ms.keywords: WdfUsbTargetDeviceQueryString
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
req.alt-api: WdfUsbTargetDeviceQueryString
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
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
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceQueryString function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceQueryString</b> method retrieves the Unicode string that is associated with a specified USB device and descriptor index value.



## -syntax

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


## -parameters

### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Request [in, optional]

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section. 


### -param RequestOptions [in, optional]

A pointer to a caller-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section. 


### -param String [out, optional]

A pointer to a caller-allocated buffer that receives the requested Unicode string. The string is NULL-terminated only if the device supplies a NULL-terminated string. If this pointer is <b>NULL</b>, <b>WdfUsbTargetDeviceQueryString</b> returns the required buffer size (that is, the required number of Unicode characters) in the location that <i>NumCharacters</i> points to.


### -param NumCharacters [in, out]

A pointer to a caller-allocated variable. The caller supplies the number of Unicode characters that the buffer can hold. When <b>WdfUsbTargetDeviceQueryString</b> returns, the variable receives the number of characters (including the NULL terminator, if supplied) that are in the Unicode string that the <i>String</i> buffer receives. 


### -param StringIndex [in]

An index value that identifies the Unicode string. This index value is obtained from a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a> structure.


### -param LangID [in, optional]

A language identifier. The Unicode string will be retrieved for the language that this identifier specifies. For information about obtaining a device's supported language identifiers, see the USB specification. 


## -returns
<b>WdfUsbTargetDeviceQueryString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A memory buffer could not be allocated.
<dl>
<dt><b>STATUS_DEVICE_DATA_ERROR</b></dt>
</dl>The USB device returned an invalid descriptor.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>The supplied buffer was too small.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Drivers should call <b>WdfUsbTargetDeviceQueryString</b> twice, by using the following steps:

Set the <i>String</i> pointer to <b>NULL</b>, so that <b>WdfUsbTargetDeviceQueryString</b> will return the required buffer size in the address that the <i>NumCharacters</i> parameter points to.

 Allocate buffer space to hold the number of Unicode characters that are in the requested string. For example, a driver might call <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> to allocate a buffer, or it might call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> to create a framework memory object.

Call <b>WdfUsbTargetDeviceQueryString</b> again, setting the <i>String</i> value to a pointer to the new buffer and setting <i>NumCharacters</i> to the buffer's length (that is, the number of Unicode characters, not the byte length).

<b>WdfUsbTargetDeviceQueryString</b> locates the specified USB string descriptor and copies the Unicode string from the descriptor into the supplied buffer. 

If your driver specifies a non-<b>NULL</b> value for the <i>Request</i> parameter, the framework uses the specified request object, and another driver thread can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a>, if necessary, to attempt to cancel the string query request. If the driver specifies a <b>NULL</b> value for <i>Request</i>, the framework uses an internal request object that the driver cannot cancel. 

Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

For more information about USB string descriptors, see the USB specification.

For more information about the <b>WdfUsbTargetDeviceQueryString</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

The following code example calls <b>WdfUsbTargetDeviceQueryString</b> to obtain the required buffer size, calls <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> to create a memory object and buffer, and then calls <b>WdfUsbTargetDeviceQueryString</b> again to obtain the manufacturer's name string, in USA English (0x0409), from a USB device descriptor. (The driver previously stored the descriptor in driver-defined context space.)


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceallocandquerystring.md">WdfUsbTargetDeviceAllocAndQueryString</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceQueryString method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

