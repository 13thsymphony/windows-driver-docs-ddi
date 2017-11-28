---
UID: NS.hbapiwmi._ScsiInquiry_IN
title: ScsiInquiry_IN
author: windows-driver-content
description: The ScsiInquiry_IN structure is used by a miniport driver to deliver input parameter data to the ScsiInquiry WMI method.
old-location: storage\scsiinquiry_in2.htm
old-project: storage
ms.assetid: f7690483-8269-4fb4-9960-9abdbb128b94
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ScsiInquiry_IN, ScsiInquiry_IN, *PScsiInquiry_IN
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
req.alt-api: ScsiInquiry_IN
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

# ScsiInquiry_IN structure



## -description
<p>The ScsiInquiry_IN structure is used by a miniport driver to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a> WMI method. </p>


## -syntax

````
typedef struct _ScsiInquiry_IN {
  UCHAR     Cdb[6];
  UCHAR     HbaPortWWN[8];
  UCHAR     DiscoveredPortWWN[8];
  ULONGLONG FcLun;
} ScsiInquiry_IN, *PScsiInquiry_IN;
````


## -struct-fields
<dl>

### -field <b>Cdb</b>

<dd>
<p>Contains the command descriptor block that holds the SCSI inquiry command to be sent to the target device. </p>
</dd>

### -field <b>HbaPortWWN</b>

<dd>
<p>Contains a worldwise name for the HBA through which the target is accessed. </p>
</dd>

### -field <b>DiscoveredPortWWN</b>

<dd>
<p>Contains a worldwide name for the port through which the target device is accessed. </p>
</dd>

### -field <b>FcLun</b>

<dd>
<p>Indicates the logical unit number of the logical unit that will receive the SCSI inquiry command.</p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the ScsiInquiry_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiInquiry_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
