---
UID: NF:usbdlib.USBD_ParseDescriptors
title: USBD_ParseDescriptors function
author: windows-driver-content
description: The USBD_ParseDescriptors routine searches a given configuration descriptor and returns a pointer to the first descriptor that matches the search criteria.
old-location: buses\usbd_parsedescriptors.htm
old-project: usbref
ms.assetid: d6d90a4a-a67d-4ef3-82b8-7146970e30f3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: USBD_ParseDescriptors
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBD_ParseDescriptors
req.alt-loc: Usbd.lib,Usbd.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbd.lib
req.dll: 
req.irql: < DISPATCH_LEVEL
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_ParseDescriptors function



## -description

   The <b>USBD_ParseDescriptors</b> routine searches a given configuration descriptor and returns a pointer to the first descriptor that matches the search criteria.



## -syntax

````
PUSB_COMMON_DESCRIPTOR USBD_ParseDescriptors(
  _In_ PVOID DescriptorBuffer,
  _In_ ULONG TotalLength,
  _In_ PVOID StartPosition,
  _In_ LONG  DescriptorType
);
````


## -parameters

### -param DescriptorBuffer [in]

Pointer to a configuration descriptor that contains the descriptor for which to search.


### -param TotalLength [in]

Specifies the size, in bytes, of the buffer pointed to by <i>DescriptorBuffer</i>.


### -param StartPosition [in]

Pointer to the address within the configuration descriptor, provided at <i>DescriptorBuffer</i>, to begin searching from. To search from the beginning of the configuration descriptor, the parameters <i>DescriptorBuffer</i> and <i>StartPosition</i> must be the same address.


### -param DescriptorType [in]

Specifies the descriptor type code as assigned by USB. The following values are valid for USB-defined descriptor types:




### -param USB_STRING_DESCRIPTOR_TYPE

Specifies that the descriptor being searched for is a string descriptor.


### -param USB_INTERFACE_DESCRIPTOR_TYPE

Specifies that the descriptor being searched for is an interface descriptor.


### -param USB_ENDPOINT_DESCRIPTOR_TYPE

Specifies that the descriptor being searched for is an endpoint descriptor.

</dd>
</dl>

## -returns
<b>USBD_ParseDescriptors</b> returns a pointer to a <a href="..\usbspec\ns-usbspec-_usb_common_descriptor.md">USB_COMMON_DESCRIPTOR</a> structure that is the head of the first descriptor that matches the given search criteria, or <b>NULL</b> is returned if no match is found:


## -remarks
This structure is used to hold a portion of a descriptor, so that the caller of <b>USBD_ParseDescriptors</b> can determine the correct structure to use to access the remaining data in the descriptor. Every descriptor type has these fields at the beginning of the data and callers can use the <b>bLength</b> and <b>bDescriptorType</b> members to correctly identify the type of this descriptor.

When this routine parses the configuration descriptor looking for the descriptor that matches the search criteria, it returns the first match, terminating the search.


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
Header

</th>
<td width="70%">
<dl>
<dt>Usbdlib.h (include Usbdlib.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Usbd.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt; DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="usb_reference.htm#client">USB device driver programming reference</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_ParseDescriptors routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

