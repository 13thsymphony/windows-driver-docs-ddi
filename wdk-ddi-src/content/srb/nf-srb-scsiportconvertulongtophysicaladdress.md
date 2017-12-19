---
UID: NF.srb.ScsiPortConvertUlongToPhysicalAddress
title: ScsiPortConvertUlongToPhysicalAddress function
author: windows-driver-content
description: The ScsiPortConvertUlongToPhysicalAddress routine extends a given ULONG address into a value of type SCSI_PHYSICAL_ADDRESS.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportconvertulongtophysicaladdress.htm
old-project: storage
ms.assetid: 98d491f8-eeb5-4152-9bb6-fffabcba0360
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ScsiPortConvertUlongToPhysicalAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiPortConvertUlongToPhysicalAddress
req.alt-loc: Scsiport.lib,Scsiport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Scsiport.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# ScsiPortConvertUlongToPhysicalAddress function



## -description
The <b>ScsiPortConvertUlongToPhysicalAddress</b> routine extends a given ULONG address into a value of type SCSI_PHYSICAL_ADDRESS.



## -syntax

````
SCSI_PHYSICAL_ADDRESS ScsiPortConvertUlongToPhysicalAddress(
  _In_ ULONG_PTR UlongAddress
);
````


## -parameters

### -param UlongAddress [in]

Specifies a value of type ULONG.


## -returns
<b>ScsiPortConvertUlongToPhysicalAddress</b> returns the converted SCSI_PHYSICAL_ADDRESS.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Srb.h (include Miniport.h or Scsi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Scsiport.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.access_range">ACCESS_RANGE</a>
</dt>
<dt>
<a href="storage.scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
</dt>
<dt>
<a href="storage.scsiportgetvirtualaddress">ScsiPortGetVirtualAddress</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortConvertUlongToPhysicalAddress routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

