---
UID: NS.hbapiwmi._ScsiReadCapacity_OUT
title: ScsiReadCapacity_OUT
author: windows-driver-content
description: The ScsiReadCapacity_OUT structure is used to report the output data of the ScsiReadCapacity WMI method to the WMI client.
old-location: storage\scsireadcapacity_out2.htm
old-project: storage
ms.assetid: bf295061-42d6-4f2e-a39e-9bac440b0d93
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ScsiReadCapacity_OUT, ScsiReadCapacity_OUT, *PScsiReadCapacity_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiReadCapacity_OUT
req.alt-loc: Hbapiwmi.h
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

# ScsiReadCapacity_OUT structure



## -description
<p>The ScsiReadCapacity_OUT structure is used to report the output data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564890">ScsiReadCapacity</a> WMI method to the WMI client.</p>


## -syntax

````
typedef struct _ScsiReadCapacity_OUT {
  ULONG HBAStatus;
  ULONG ResponseBufferSize;
  ULONG SenseBufferSize;
  UCHAR ScsiStatus;
  UCHAR ResponseBuffer[1];
  UCHAR SenseBuffer[1];
} ScsiReadCapacity_OUT, *PScsiReadCapacity_OUT;
````


## -struct-fields
<dl>

### -field <b>HBAStatus</b>

<dd>
<p>Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation. </p>
</dd>

### -field <b>ResponseBufferSize</b>

<dd>
<p>Indicates the size in bytes of the buffer that will hold the results of the read capacity command. </p>
</dd>

### -field <b>SenseBufferSize</b>

<dd>
<p>Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the read capacity command. </p>
</dd>

### -field <b>ScsiStatus</b>

<dd>
<p>Contains the status of the SCSI read capacity command. </p>
</dd>

### -field <b>ResponseBuffer</b>

<dd>
<p>Contains the results of the SCSI read capacity command. </p>
</dd>

### -field <b>SenseBuffer</b>

<dd>
<p>Contains the SCSI sense data that results from the SCSI read capacity command. </p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the ScsiReadCapacity_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564890">ScsiReadCapacity</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiReadCapacity_OUT structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
