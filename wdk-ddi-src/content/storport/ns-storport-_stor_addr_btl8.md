---
UID: NS.STORPORT._STOR_ADDR_BTL8
title: _STOR_ADDR_BTL8
author: windows-driver-content
description: The STOR_ADDR_BTL8 address structure contains the addressing information for an 8-bit Bus-Target-LUN (BTL8) address.
old-location: storage\stor_addr_btl8.htm
old-project: storage
ms.assetid: 53C8A5D4-4D8B-4D3E-A350-B3BBAC7F8C71
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _STOR_ADDR_BTL8, *PSTOR_ADDR_BTL8, STOR_ADDR_BTL8
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
req.alt-api: STOR_ADDR_BTL8
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

# _STOR_ADDR_BTL8 structure



## -description

   The <b>STOR_ADDR_BTL8</b> address structure contains the addressing information for an 8-bit Bus-Target-LUN (BTL8) address.
  



## -syntax

````
typedef struct _STOR_ADDR_BTL8 {
  USHORT Type;
  USHORT Port;
  ULONG  AddressLength;
  UCHAR  Path;
  UCHAR  Target;
  UCHAR  Lun;
  UCHAR  Reserved;
} STOR_ADDR_BTL8, *PSTOR_ADDR_BTL8;
````


## -struct-fields

### -field Type

The address type. This member is set to <b>STOR_ADDRESS_TYPE_BTL8</b>.


### -field Port

The host bus adapter (HBA) port number.


### -field AddressLength

The byte length of the address. This value is set to <b>STOR_ADDR_BTL8_ADDRESS_LENGTH</b>.


### -field Path

The bus number for the target device.


### -field Target

The target device number.


### -field Lun

The logical unit on the target device.


### -field Reserved

Reserved, set to 0.


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
<a href="storage.stor_address">STOR_ADDRESS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_ADDR_BTL8 structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

