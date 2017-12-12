---
UID: NS.NTDDTAPE._TAPE_GET_POSITION
title: _TAPE_GET_POSITION
author: windows-driver-content
description: The TAPE_GET_POSITION structure is used in conjunction with the IOCTL_TAPE_GET_POSITION request to retrieve the current absolute, logical, or pseudological partition and offset position on the tape.
old-location: storage\tape_get_position.htm
old-project: storage
ms.assetid: dd7a194a-6ce4-4889-b574-7c4f232f45f0
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _TAPE_GET_POSITION, *PTAPE_GET_POSITION, TAPE_GET_POSITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddtape.h
req.include-header: Ntddtape.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TAPE_GET_POSITION
req.alt-loc: ntddtape.h
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

# _TAPE_GET_POSITION structure



## -description
The TAPE_GET_POSITION structure is used in conjunction with the <a href="..\ntddtape\ni-ntddtape-ioctl_tape_get_position.md">IOCTL_TAPE_GET_POSITION</a> request to retrieve the current absolute, logical, or pseudological partition and offset position on the tape.



## -syntax

````
typedef struct _TAPE_GET_POSITION {
  ULONG         Type;
  ULONG         Partition;
  LARGE_INTEGER Offset;
} TAPE_GET_POSITION, *PTAPE_GET_POSITION;
````


## -struct-fields

### -field Type

Indicates the type of position requested. This member can be TAPE_ABSOLUTE_POSITION, TAPE_LOGICAL_POSITION, or TAPE_PSEUDO_LOGICAL_POSITION.


### -field Partition

Indicates the number of the partition where the current position is located.


### -field Offset

Indicates the number of bytes from the beginning of the partition to the current position.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddtape.h (include Ntddtape.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddtape\ni-ntddtape-ioctl_tape_get_position.md">IOCTL_TAPE_GET_POSITION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_GET_POSITION structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

