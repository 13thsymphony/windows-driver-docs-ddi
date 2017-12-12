---
UID: NI.ntddcdvd.IOCTL_AACS_READ_VOLUME_ID
title: IOCTL_AACS_READ_VOLUME_ID
author: windows-driver-content
description: Reads the Advanced Access Content System (AACS)-specific volume identifier.
old-location: storage\ioctl_aacs_read_volume_id.htm
old-project: storage
ms.assetid: 8772a83a-06e3-48f8-9d41-47332122ec8b
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: DVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_AACS_READ_VOLUME_ID
req.alt-loc: Ntddcdvd.h
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

# IOCTL_AACS_READ_VOLUME_ID IOCTL



## -description
Reads the Advanced Access Content System (AACS)-specific volume identifier. 



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a value of type <a href="storage.dvd_session_id">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID). The AGID identifies the secure session that is associated with the volume.


### -input-buffer-length
Length of a <a href="storage.dvd_session_id">DVD_SESSION_ID</a>.


### -output-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the value of type <a href="storage.aacs_volume_id">AACS_VOLUME_ID</a> that specifies the volume ID. 


### -output-buffer-length
Length of a <a href="storage.aacs_volume_id">AACS_VOLUME_ID</a>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks
The IOCTL_AACS_READ_VOLUME_ID request corresponds to the part of the AACS authentication protocol that is responsible for transfering the volume identifier. For a complete description of this protocol, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA). 

The AGID is automatically released after the IOCTL_AACS_READ_VOLUME_ID request completes. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddcdvd.h (include Ntddcdvd.h)</dt>
</dl>
</td>
</tr>
</table>