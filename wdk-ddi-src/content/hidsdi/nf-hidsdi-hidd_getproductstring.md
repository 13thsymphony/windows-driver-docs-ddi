---
UID: NF.hidsdi.HidD_GetProductString
title: HidD_GetProductString function
author: windows-driver-content
description: The HidD_GetProductString routine returns the embedded string of a top-level collection that identifies the manufacturer's product.
old-location: hid\hidd_getproductstring.htm
old-project: hid
ms.assetid: c0627fbf-4b64-4530-8c0f-45326a83f765
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: HidD_GetProductString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HidD_GetProductString
req.alt-loc: Hid.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
---

# HidD_GetProductString function



## -description
The <b>HidD_GetProductString</b> routine returns the embedded string of a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> that identifies the manufacturer's product.


## -syntax

````
BOOLEAN __stdcall HidD_GetProductString(
  _In_  HANDLE HidDeviceObject,
  _Out_ PVOID  Buffer,
  _In_  ULONG  BufferLength
);
````


## -parameters

### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.

### -param Buffer [out]

Pointer to a caller-allocated buffer that the routine uses to return the requested product string. The routine returns a NULL-terminated wide character string.

### -param BufferLength [in]

Specifies the length, in bytes, of a caller-allocated buffer provided at <i>Buffer</i>. If the buffer is not large enough to return the entire NULL-terminated embedded string, the routine returns nothing in the buffer.

## -returns
<b>HidD_GetProductString</b> returns <b>TRUE</b> if it successfully returns the entire NULL-terminated embedded string. Otherwise, the routine returns <b>FALSE</b>.

## -remarks
Only user-mode applications can call <b>HidD_GetProductString</b>. Kernel-mode drivers can use an <a href="..\hidclass\ni-hidclass-ioctl_hid_get_product_string.md">IOCTL_HID_GET_PRODUCT_STRING</a> request.

The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

The <b>iProduct</b> member of a <a href="buses.usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a> structure for a particular interface is set by the <a href="buses.usb_common_class_generic_parent_driver">USB common class generic parent driver</a> based on the following rules:

If the <b>iInterface</b> member of the <a href="buses.usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> structure for the interface is nonzero, the <b>iProduct</b> member of the USB_DEVICE_DESCRIPTOR structure for the interface is set to the <b>iInterface</b> member of the USB_INTERFACE_DESCRIPTOR structure.

If the interface is grouped by a <a href="buses.usb_interface_association_descriptor">USB interface association descriptor</a>, and the <b>iFunction</b> member of the interface association descriptor for the interface is nonzero, the <b>iProduct</b> member of the USB_DEVICE_DESCRIPTOR structure for the interface is set to the <b>iFunction</b> member of the interface association descriptor.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows 2000 and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Hidsdi.h (include Hidsdi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Hid.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Hid.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="hid.hidd_getindexedstring">HidD_GetIndexedString</a>
</dt>
<dt>
<a href="hid.hidd_getphysicaldescriptor">HidD_GetPhysicalDescriptor</a>
</dt>
<dt>
<a href="hid.hidd_getserialnumberstring">HidD_GetSerialNumberString</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_indexed_string.md">IOCTL_HID_GET_INDEXED_STRING</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_manufacturer_string.md">IOCTL_HID_GET_MANUFACTURER_STRING</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_product_string.md">IOCTL_HID_GET_PRODUCT_STRING</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_serialnumber_string.md">IOCTL_HID_GET_SERIALNUMBER_STRING</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_GetProductString routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
