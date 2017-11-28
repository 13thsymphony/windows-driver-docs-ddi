---
UID: NS.1394._ADDRESS_RANGE
title: ADDRESS_RANGE
author: windows-driver-content
description: The ADDRESS_RANGE structure describes a range in a IEEE 1394 device's address space.
old-location: ieee\address_range.htm
old-project: IEEE
ms.assetid: 4eeb543b-0c23-4119-8e42-ff086b4b7682
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: ADDRESS_RANGE, ADDRESS_RANGE, *PADDRESS_RANGE
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
req.alt-api: ADDRESS_RANGE
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
---

# ADDRESS_RANGE structure



## -description
<p>The ADDRESS_RANGE structure describes a range in a IEEE 1394 device's address space.</p>


## -syntax

````
typedef struct _ADDRESS_RANGE {
  USHORT AR_Off_High;
  USHORT AR_Length;
  ULONG  AR_Off_Low;
} ADDRESS_RANGE, *PADDRESS_RANGE;
````


## -struct-fields
<dl>

### -field <b>AR_Off_High</b>

<dd>
<p>Specifies the high order bits of the 1394 address within the buffer.</p>
</dd>

### -field <b>AR_Length</b>

<dd>
<p>Specifies the length, in bytes, of a 1394 address buffer.</p>
</dd>

### -field <b>AR_Off_Low</b>

<dd>
<p>Specifies the low order bits of the 1394 address within the buffer.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537640">REQUEST_FREE_ADDRESS_RANGE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20ADDRESS_RANGE structure%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
