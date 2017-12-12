---
UID: NI.ntddcdvd.IOCTL_AACS_GENERATE_BINDING_NONCE
title: IOCTL_AACS_GENERATE_BINDING_NONCE
author: windows-driver-content
description: Reads the Advanced Access Content System (AACS) binding nonce starting at the specified byte offset on the disc, as part of the protocol for writing to a protected data area.
old-location: storage\ioctl_aacs_generate_binding_nonce.htm
old-project: storage
ms.assetid: bb0fec4e-e6be-46e1-b6be-253dd0579ca6
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
req.alt-api: IOCTL_AACS_GENERATE_BINDING_NONCE
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

# IOCTL_AACS_GENERATE_BINDING_NONCE IOCTL



## -description
Reads the Advanced Access Content System (AACS) binding nonce starting at the specified byte offset on the disc, as part of the protocol for writing to a protected data area.



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a structure of type <a href="storage.aacs_read_binding_nonce">AACS_READ_BINDING_NONCE</a> that specifies the <a href="storage.dvd_session_id">DVD_SESSION_ID</a>, the starting logical block address and the number of sectors for which the logical unit should generate a binding nonce.


### -input-buffer-length
Length of an <a href="storage.aacs_read_binding_nonce">AACS_READ_BINDING_NONCE</a>.


### -output-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the value of type <a href="storage.aacs_binding_nonce">AACS_BINDING_NONCE</a> that specifies the binding nonce.


### -output-buffer-length
Length of an <a href="storage.aacs_binding_nonce">AACS_BINDING_NONCE</a>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks
The IOCTL_AACS_GENERATE_BINDING_NONCE request corresponds to the part of the AACS authentication protocol that is responsible for writing to a protected data area. For a complete description of this protocol, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).

The IOCTL_AACS_GENERATE_BINDING_NONCE request requires a single available AGID during its processing, and the AGID is <b><i>not</i></b> automatically released after the request completes. The AGID remains valid until it is explicitly invalidated or until the drive generates a power-on reset, hard reset, or media ejection event. However, the AGID cannot be reused with other requests.

It is recommended that you wait for the completion of all other requests that use secure sessions with AGIDs before making an IOCTL_AACS_GENERATE_BINDING_NONCE request.

Clients that do not use file system support must set the <b>Handle</b> member of <a href="storage.aacs_read_binding_nonce">AACS_READ_BINDING_NONCE</a> to INVALID_HANDLE_VALUE and specify explicit values for the <b>StartLBA</b> and <b>NumberOfSectors</b> members.


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