---
UID: NS.hbapiwmi._HBAFCPScsiEntry
title: HBAFCPScsiEntry
author: windows-driver-content
description: The HBAFCPScsiEntry structure is used with GetFcpTargetMapping method of the MSFC_HBAFCPInfo WMI Class to define a binding between the operating system information that uniquely identifies a logical unit and the fibre channel protocol (FCP) identifier that identifies the logical unit.
old-location: storage\hbafcpscsientry.htm
old-project: storage
ms.assetid: 718431f9-e4cc-4e79-84d3-a59f5399e711
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBAFCPScsiEntry, HBAFCPScsiEntry, *PHBAFCPScsiEntry
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
req.alt-api: HBAFCPScsiEntry
req.alt-loc: hbapiwmi.h
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

# HBAFCPScsiEntry structure



## -description
<p>The HBAFCPScsiEntry structure is used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a> to define a binding between the operating system information that uniquely identifies a logical unit and the fibre channel protocol (FCP) identifier that identifies the logical unit.  </p>


## -syntax

````
typedef struct _HBAFCPScsiEntry {
  HBAFCPID  FCPId;
  UCHAR     Luid[256];
  HBAScsiID ScsiId;
} HBAFCPScsiEntry, *PHBAFCPScsiEntry;
````


## -struct-fields
<dl>

### -field <b>FCPId</b>

<dd>
<p>Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556038">HBAFCPID</a> that contains the FCP identifier for the logical unit and information about the port to be queried for information about the device.</p>
</dd>

### -field <b>Luid</b>

<dd>
<p>Contains the logical unit descriptor for the device that the operating system derives from SCSI inquiry data. </p>
</dd>

### -field <b>ScsiId</b>

<dd>
<p>Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556042">HBAScsiID</a> that contains the information that uniquely identifies a logical unit for the operating system. </p>
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
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBAFCPScsiEntry structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
