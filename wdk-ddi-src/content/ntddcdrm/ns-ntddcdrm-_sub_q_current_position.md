---
UID: NS.NTDDCDRM._SUB_Q_CURRENT_POSITION
title: _SUB_Q_CURRENT_POSITION
author: windows-driver-content
description: The SUB_Q_CURRENT_POSITION structure contains position information and is used in conjunction with SUB_Q_CHANNEL_DATA.
old-location: storage\sub_q_current_position.htm
old-project: storage
ms.assetid: 816baec4-3dd0-4025-ba34-035bf6f241d3
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _SUB_Q_CURRENT_POSITION, *PSUB_Q_CURRENT_POSITION, SUB_Q_CURRENT_POSITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SUB_Q_CURRENT_POSITION
req.alt-loc: ntddcdrm.h
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

# _SUB_Q_CURRENT_POSITION structure



## -description
The SUB_Q_CURRENT_POSITION structure contains position information and is used in conjunction with <a href="storage.sub_q_channel_data">SUB_Q_CHANNEL_DATA</a>. 


## -syntax

````
typedef struct _SUB_Q_CURRENT_POSITION {
  SUB_Q_HEADER Header;
  UCHAR        FormatCode;
  UCHAR        Control  :4;
  UCHAR        ADR  :4;
  UCHAR        TrackNumber;
  UCHAR        IndexNumber;
  UCHAR        AbsoluteAddress[4];
  UCHAR        TrackRelativeAddress[4];
} SUB_Q_CURRENT_POSITION, *PSUB_Q_CURRENT_POSITION;
````


## -struct-fields

### -field Header

Indicates, among other things, the length of the Q subchannel data that was retrieved. See <a href="storage.sub_q_header">SUB_Q_HEADER</a> for more details. 

### -field FormatCode

Should have a value of IOCTL_CDROM_CURRENT_POSITION. 

### -field Control

Defines various types of information within the table of contents lead-in area. For more information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS). 

### -field ADR

Indicates the type of information encoded in the Q subchannel of the block. For information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS). 

### -field TrackNumber

Contains the current track number.

### -field IndexNumber

Contains the current index number.

### -field AbsoluteAddress

Gives the current location relative to the logical beginning of the media. The bytes in this array are arranged in big-endian order. <b>AbsoluteAddress</b>[0] contains the most significant byte, and <b>AbsoluteAddress</b>[3] contains the least significant byte. 

### -field TrackRelativeAddress

Gives the current location relative to the logical beginning of the current track. The bytes in this array are arranged in big-endian order. <b>TrackRelativeAddress</b>[0] contains the most significant byte, and <b>TrackRelativeAddress</b>[3] contains the least significant byte. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_q_channel.md">IOCTL_CDROM_READ_Q_CHANNEL</a>
</dt>
<dt>
<a href="storage.cdrom_sub_q_data_format">CDROM_SUB_Q_DATA_FORMAT</a>
</dt>
<dt>
<a href="storage.sub_q_channel_data">SUB_Q_CHANNEL_DATA</a>
</dt>
<dt>
<a href="storage.sub_q_header">SUB_Q_HEADER</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SUB_Q_CURRENT_POSITION structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
