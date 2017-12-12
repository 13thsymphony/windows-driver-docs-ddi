---
UID: NF.storport.StorPortGetSystemPortNumber
title: StorPortGetSystemPortNumber function
author: windows-driver-content
description: The StorPortGetSystemPortNumber routine retrieves the system assigned port number for a storage adapter.
old-location: storage\storportgetsystemportnumber.htm
old-project: storage
ms.assetid: D1205C85-6F23-4D08-A146-2FA8C00FD6E9
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: StorPortGetSystemPortNumber
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortGetSystemPortNumber
req.alt-loc: storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# StorPortGetSystemPortNumber function



## -description
The <b>StorPortGetSystemPortNumber</b> routine retrieves the system assigned port number for a storage adapter.



## -syntax

````
ULONG StorPortGetSystemPortNumber(
  _In_    PVOID         HwDeviceExtension,
  _Inout_ PSTOR_ADDRESS Address
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Address [in, out]

A pointer to a storage address structure formatted as <a href="storage.stor_addr_btl8">STOR_ADDR_BTL8</a>. On return, the <b>Port</b> member of this structure will contain the port value assigned to the adapter.


## -returns
<b>StorPortGetSystemPortNumber</b> returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>A port number value is not yet assigned to the storage adapter.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>Indicates that port number of the  storage adapter was returned successfully.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>HwDeviceExtension</i> was <b>NULL</b>.

-or-

The <b>Type</b> member of <i>Address</i> is not <b>STOR_ADDRESS_TYPE_BTL8</b>.

 


## -remarks
The address structure pointed to by <i>Address</i> is allocated and formatted as <a href="storage.stor_addr_btl8">STOR_ADDR_BTL8</a>. The <b>Type</b> member of <i>Address</i> must be set to <b>STOR_ADDRESS_TYPE_BTL8</b> and the <b>Length</b> member <i>Address</i> must be greater than or equal to <b>STOR_ADDR_BTL8_ADDRESS_LENGTH</b>.


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
Available in starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.stor_addr_btl8">STOR_ADDR_BTL8</a>
</dt>
<dt>
<a href="storage.stor_address">STOR_ADDRESS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetSystemPortNumber routine%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

