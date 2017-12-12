---
UID: NI.ntddcdvd.IOCTL_AACS_GET_CERTIFICATE
title: IOCTL_AACS_GET_CERTIFICATE
author: windows-driver-content
description: Queries the logical unit for the device certificate.
old-location: storage\ioctl_aacs_get_certificate.htm
old-project: storage
ms.assetid: 1245f9c3-702c-48d8-8ecd-c0ce40d520b3
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
req.alt-api: IOCTL_AACS_GET_CERTIFICATE
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

# IOCTL_AACS_GET_CERTIFICATE IOCTL



## -description
Queries the logical unit for the device certificate. 



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a value of type <a href="storage.dvd_session_id">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID). The AGID identifies the secure session.


### -input-buffer-length
Length of a <a href="storage.dvd_session_id">DVD_SESSION_ID</a>.


### -output-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the drive certificate with a format of <a href="storage.aacs_certificate">AACS_CERTIFICATE</a>.


### -output-buffer-length
Length of an <a href="storage.aacs_certificate">AACS_CERTIFICATE</a>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks
The IOCTL_AACS_GET_CERTIFICATE request corresponds to the step of the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth) in which the drive provides its certificate and nonce to the host. For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA). 


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