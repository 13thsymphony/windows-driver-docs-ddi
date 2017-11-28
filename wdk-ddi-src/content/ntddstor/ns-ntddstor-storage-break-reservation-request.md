---
UID: NS.ntddstor.STORAGE_BREAK_RESERVATION_REQUEST
title: STORAGE_BREAK_RESERVATION_REQUEST
author: windows-driver-content
description: The STORAGE_BREAK_RESERVATION_REQUEST structure is used in conjunction with the IOCTL_STORAGE_BREAK_RESERVATION request to free a disk resource that was previously reserved.
old-location: storage\storage_break_reservation_request.htm
old-project: storage
ms.assetid: 06de4432-9437-4275-8d1e-606f209e1468
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: STORAGE_BREAK_RESERVATION_REQUEST, STORAGE_BREAK_RESERVATION_REQUEST, *PSTORAGE_BREAK_RESERVATION_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_BREAK_RESERVATION_REQUEST
req.alt-loc: ntddstor.h
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
req.iface: 
---

# STORAGE_BREAK_RESERVATION_REQUEST structure



## -description
<p>The STORAGE_BREAK_RESERVATION_REQUEST structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560533">IOCTL_STORAGE_BREAK_RESERVATION</a> request to free a disk resource that was previously reserved. </p>


## -syntax

````
typedef struct STORAGE_BREAK_RESERVATION_REQUEST {
  ULONG Length;
  UCHAR _unused;
  UCHAR PathId;
  UCHAR TargetId;
  UCHAR Lun;
} STORAGE_BREAK_RESERVATION_REQUEST, *PSTORAGE_BREAK_RESERVATION_REQUEST;
````


## -struct-fields
<dl>

### -field <b>Length</b>

<dd>
<p>Contains the length of this structure in bytes.</p>
</dd>

### -field <b>_unused</b>

<dd>
<p>Reserved. Do not use. </p>
</dd>

### -field <b>PathId</b>

<dd>
<p>Indicates the number of the bus to be reset. </p>
</dd>

### -field <b>TargetId</b>

<dd>
<p>Contains the number of the target device.</p>
</dd>

### -field <b>Lun</b>

<dd>
<p>Contains the logical unit number. </p>
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
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560533">IOCTL_STORAGE_BREAK_RESERVATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_BREAK_RESERVATION_REQUEST structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
