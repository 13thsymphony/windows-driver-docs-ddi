---
UID: NF:wdfusb.WdfUsbTargetDeviceAllocAndQueryString
title: WdfUsbTargetDeviceAllocAndQueryString function
author: windows-driver-content
description: The WdfUsbTargetDeviceAllocAndQueryString method allocates a buffer, then it retrieves the Unicode string that is associated with a specified USB device and descriptor index value.
old-location: wdf\wdfusbtargetdeviceallocandquerystring.htm
old-project: wdf
ms.assetid: a9dea258-601b-4ff7-b03b-b3f22d86f314
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfusb/WdfUsbTargetDeviceAllocAndQueryString, DFUsbRef_708583a1-a585-402f-afd6-5df4457b0a25.xml, WdfUsbTargetDeviceAllocAndQueryString method, PFN_WDFUSBTARGETDEVICEALLOCANDQUERYSTRING, WdfUsbTargetDeviceAllocAndQueryString, kmdf.wdfusbtargetdeviceallocandquerystring, wdf.wdfusbtargetdeviceallocandquerystring
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
-	WdfUsbTargetDeviceAllocAndQueryString
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---


# WdfUsbTargetDeviceAllocAndQueryString function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceAllocAndQueryString</b> method allocates a buffer, then it retrieves the Unicode string that is associated with a specified USB device and descriptor index value.

## Syntax

````
NTSTATUS WdfUsbTargetDeviceAllocAndQueryString(
  _In_      WDFUSBDEVICE           UsbDevice,
  _In_opt_  PWDF_OBJECT_ATTRIBUTES StringMemoryAttributes,
  _Out_     WDFMEMORY              *StringMemory,
  _Out_opt_ PUSHORT                NumCharacters,
  _In_      UCHAR                  StringIndex,
  _In_opt_  USHORT                 LangID
);
````

## Parameters

`UsbDevice`

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.

`StringMemoryAttributes`

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains caller-supplied attributes for the new memory object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

`StringMemory`

A pointer to a location that receives a handle to the memory object that contains the Unicode string. The string is NULL-terminated only if the device supplies a NULL-terminated string.

`NumCharacters`

A pointer to a location that receives the number of characters that are contained in the string descriptor. If the Unicode string is NULL-terminated, this number includes the NULL character. This parameter is optional and can be <b>NULL</b>.

`StringIndex`

An index value that identifies the Unicode string. This index value is obtained from a <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>, <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>, or <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure.

`LangID`

A language identifier. The Unicode string will be retrieved for the language that this identifier specifies. For information about obtaining a device's supported language identifiers, see the USB specification.


## Return Value

<b>WdfUsbTargetDeviceAllocAndQueryString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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

The <b>WdfUsbTargetDeviceAllocAndQueryString</b> method, which your driver only needs to call once to obtain a string descriptor, is an alternative to the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicequerystring.md">WdfUsbTargetDeviceQueryString</a> method, which must be called twice to obtain a string.

The method locates the specified USB string descriptor, copies the Unicode string from the descriptor into a memory object, and returns a handle to the memory object. 

After calling <b>WdfUsbTargetDeviceAllocAndQueryString</b>, your driver can pass the <i>StringMemory</i> handle to <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a> to access the contents of the memory object.

For more information about USB string descriptors, see the USB specification.

For more information about the <b>WdfUsbTargetDeviceAllocAndQueryString</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example calls <b>WdfUsbTargetDeviceAllocAndQueryString</b> to obtain a manufacturer's name string, in USA English (0x0409), from a USB device descriptor. (The driver previously stored the descriptor in driver-defined context space.)

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PMY_DEVICE_CONTEXT  myDeviceContext;
WDFMEMORY  memoryHandle;
USHORT  numCharacters;

myDeviceContext = GetDeviceContext(device);

status = WdfUsbTargetDeviceAllocAndQueryString(
                                        myDeviceContext-&gt;UsbTargetDevice,
                                        WDF_NO_OBJECT_ATTRIBUTES,
                                        &amp;memoryHandle,
                                        &amp;numCharacters,
                                        myDeviceContext-&gt;UsbDeviceDescr.iManufacturer,
                                        0x0409
                                        );</pre>
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
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>



<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicequerystring.md">WdfUsbTargetDeviceQueryString</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceAllocAndQueryString method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>