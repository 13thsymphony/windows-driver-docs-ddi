---
UID: NS:1394._ADDRESS_OFFSET
title: _ADDRESS_OFFSET
author: windows-driver-content
description: The ADDRESS_OFFSET structure specifies the 48-bit address within a device's IEEE 1394 address space.
old-location: ieee\address_offset.htm
old-project: IEEE
ms.assetid: e1ee536f-40e4-48b7-b2d0-6ead22520ec8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _ADDRESS_OFFSET, ADDRESS_OFFSET, *PADDRESS_OFFSET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ADDRESS_OFFSET
req.alt-loc: 1394.h
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
req.typenames: ADDRESS_OFFSET, *PADDRESS_OFFSET
---

# _ADDRESS_OFFSET structure



## -description
The ADDRESS_OFFSET structure specifies the 48-bit address within a device's IEEE 1394 address space.



## -syntax

````
typedef struct _ADDRESS_OFFSET {
  USHORT Off_High;
  ULONG  Off_Low;
} ADDRESS_OFFSET, *PADDRESS_OFFSET;
````


## -struct-fields

### -field Off_High

Specifies the high order offset for a IEEE 1394 address.


### -field Off_Low

Specifies the low order offset for a IEEE 1394 address.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>1394.h (include 1394.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537155">GET_LOCAL_HOST_INFO6</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537346">IO_ADDRESS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20ADDRESS_OFFSET structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

