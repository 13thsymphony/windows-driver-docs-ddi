---
UID: NS.STORPORT._STOR_ADDRESS
title: _STOR_ADDRESS
author: windows-driver-content
description: A general structure for holding a storage device address.
old-location: storage\stor_address.htm
old-project: storage
ms.assetid: 464AE3EA-D941-430F-8362-B66F4D00AE50
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _STOR_ADDRESS, STOR_ADDRESS, *PSTOR_ADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Scsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_ADDRESS
req.alt-loc: Storport.h
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

# _STOR_ADDRESS structure



## -description

   A general structure for holding a storage device address.



## -syntax

````
typedef struct _STOR_ADDRESS {
  USHORT Type;
  USHORT Port;
  ULONG  AddressLength;
  UCHAR  AddressData[ANYSIZE_ARRAY];
} STOR_ADDRESS, *PSTOR_ADDRESS;
````


## -struct-fields

### -field Type

The address type. This can be one of the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field STOR_ADDRESS_TYPE_UNKNOWN

</td>
<td width="60%">
The address type is unknown.

</td>
</tr>
<tr>

### -field STOR_ADDRESS_TYPE_BTL8

</td>
<td width="60%">
The address is an 8-bit Bus-Target-LUN address.

</td>
</tr>
</table>
 


### -field Port

The host bus adapter (HBA) port number.


### -field AddressLength

The byte length of the <b>AddressData</b>. If <b>Type</b> is set to <b>STOR_ADDRESS_TYPE_BTL8</b>, this value is <b>STOR_ADDR_BTL8_ADDRESS_LENGTH</b>.


### -field AddressData

The address data specific to an address type.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h or Scsi.h)</dt>
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
<a href="storage.storportsetunitattributes">StorPortSetUnitAttributes</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_ADDRESS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

