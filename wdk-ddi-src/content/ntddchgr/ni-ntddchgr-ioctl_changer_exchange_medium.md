---
UID: NI:ntddchgr.IOCTL_CHANGER_EXCHANGE_MEDIUM
title: IOCTL_CHANGER_EXCHANGE_MEDIUM
author: windows-driver-content
description: Moves a piece of media from a source element to one destination and the piece of media originally in the first destination to a second destination. The source and second destination are often the same, which essentially swaps the two pieces of media.
old-location: storage\ioctl_changer_exchange_medium.htm
old-project: storage
ms.assetid: 76f17ee0-5b81-4325-a295-4a6982b49b73
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _ELEMENT_TYPE, ELEMENT_TYPE, *PELEMENT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_CHANGER_EXCHANGE_MEDIUM
req.alt-loc: Ntddchgr.h
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
req.typenames: ELEMENT_TYPE, *PELEMENT_TYPE
---

# IOCTL_CHANGER_EXCHANGE_MEDIUM IOCTL



## -description

Moves a piece of media from a source element to one destination and the piece of media originally in the first destination to a second destination. The source and second destination are often the same, which essentially swaps the two pieces of media.



Moves a piece of media from a source element to one destination and the piece of media originally in the first destination to a second destination. The source and second destination are often the same, which essentially swaps the two pieces of media.



## -ioctlparameters

### -input-buffer

        The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="..\ntddchgr\ns-ntddchgr-_changer_exchange_medium.md">CHANGER_EXCHANGE_MEDIUM</a> data, which indicates the source, both destinations, and whether either or both media should be flipped, assuming the device supports two-sided media. 


### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(CHANGER_EXCHANGE_MEDIUM).


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_DESTINATION_ELEMENT_FULL, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_ELEMENT_ADDRESS, STATUS_INVALID_PARAMETER, or STATUS_SOURCE_ELEMENT_EMPTY.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddchgr.h (include Ntddchgr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddchgr\ns-ntddchgr-_changer_exchange_medium.md">CHANGER_EXCHANGE_MEDIUM</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changerexchangemedium.md">ChangerExchangeMedium</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CHANGER_EXCHANGE_MEDIUM control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

