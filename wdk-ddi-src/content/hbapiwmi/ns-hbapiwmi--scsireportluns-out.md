---
UID: NS.hbapiwmi._ScsiReportLuns_OUT
title: ScsiReportLuns_OUT
author: windows-driver-content
description: The ScsiReportLuns_OUT structure is used to report the output parameter data of the ScsiReportLuns WMI method to the WMI client.
old-location: storage\scsireportluns_out2.htm
old-project: storage
ms.assetid: 93663b88-e750-4280-b5c1-798cc0f848b7
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ScsiReportLuns_OUT, ScsiReportLuns_OUT, *PScsiReportLuns_OUT
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
req.alt-api: ScsiReportLuns_OUT
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

# ScsiReportLuns_OUT structure



## -description
<p>The ScsiReportLuns_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564918">ScsiReportLuns</a> WMI method to the WMI client.</p>


## -syntax

````
typedef struct _ScsiReportLuns_OUT {
  ULONG HBAStatus;
  ULONG ResponseBufferSize;
  ULONG SenseBufferSize;
  UCHAR ScsiStatus;
  UCHAR ResponseBuffer[1];
  UCHAR SenseBuffer[1];
} ScsiReportLuns_OUT, *PScsiReportLuns_OUT;
````


## -struct-fields
<dl>

### -field <b>HBAStatus</b>

<dd>
<p>Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation. </p>
</dd>

### -field <b>ResponseBufferSize</b>

<dd>
<p>Indicates the size in bytes of the buffer that will hold the results of the inquiry command. </p>
</dd>

### -field <b>SenseBufferSize</b>

<dd>
<p>Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the inquiry command. </p>
</dd>

### -field <b>ScsiStatus</b>

<dd>
<p>Contains the status of the SCSI report LUNs command. </p>
</dd>

### -field <b>ResponseBuffer</b>

<dd>
<p>Contains the results of the SCSI report LUNs command. </p>
</dd>

### -field <b>SenseBuffer</b>

<dd>
<p>Contains the SCSI sense data that results from the SCSI report LUNs command. </p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the ScsiReportLuns_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564918">ScsiReportLuns</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiReportLuns_OUT structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
