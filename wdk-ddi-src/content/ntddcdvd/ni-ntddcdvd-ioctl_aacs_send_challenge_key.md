---
UID: NI.ntddcdvd.IOCTL_AACS_SEND_CHALLENGE_KEY
title: IOCTL_AACS_SEND_CHALLENGE_KEY
author: windows-driver-content
description: Sends the host's challenge key to the logical unit. The host's challenge key consists of a point on an elliptic curve and its associated signature.
old-location: storage\ioctl_aacs_send_challenge_key.htm
old-project: storage
ms.assetid: 762776f1-5423-4d02-8b59-de1e9ada8044
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
req.alt-api: IOCTL_AACS_SEND_CHALLENGE_KEY
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

# IOCTL_AACS_SEND_CHALLENGE_KEY IOCTL



## -description
Sends the host's challenge key to the logical unit. The host's challenge key consists of a point on an elliptic curve and its associated signature. 



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="storage.aacs_send_challenge_key">AACS_SEND_CHALLENGE_KEY</a> structure.


### -input-buffer-length
Length of an <a href="storage.aacs_send_challenge_key">AACS_SEND_CHALLENGE_KEY</a> structure.


### -output-buffer
None. 


### -output-buffer-length
None. 

TBD

TBD


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks
The IOCTL_AACS_SEND_CHALLENGE_KEY request corresponds to the step in the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth) in which the host provides the drive a point on the curve. For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA). 


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