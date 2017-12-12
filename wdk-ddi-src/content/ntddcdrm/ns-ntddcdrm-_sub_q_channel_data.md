---
UID: NS.NTDDCDRM._SUB_Q_CHANNEL_DATA
title: _SUB_Q_CHANNEL_DATA
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_READ_Q_CHANNEL return their output data in this union.
old-location: storage\sub_q_channel_data.htm
old-project: storage
ms.assetid: d0304ac7-cb19-499c-81af-98be33312951
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SUB_Q_CHANNEL_DATA, SUB_Q_CHANNEL_DATA, *PSUB_Q_CHANNEL_DATA
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
req.alt-api: SUB_Q_CHANNEL_DATA
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

# _SUB_Q_CHANNEL_DATA structure



## -description
Device control IRPs with a control code of IOCTL_CDROM_READ_Q_CHANNEL return their output data in this union. 



## -syntax

````
typedef union _SUB_Q_CHANNEL_DATA {
  SUB_Q_CURRENT_POSITION     CurrentPosition;
  SUB_Q_MEDIA_CATALOG_NUMBER MediaCatalog;
  SUB_Q_TRACK_ISRC           TrackIsrc;
} SUB_Q_CHANNEL_DATA, *PSUB_Q_CHANNEL_DATA;
````


## -struct-fields

### -field CurrentPosition

Contains position information, such as the absolute and relative addresses, in a <a href="storage.sub_q_current_position">SUB_Q_CURRENT_POSITION</a> structure. 


### -field MediaCatalog

Contains the media catalog number in a <a href="storage.sub_q_media_catalog_number">SUB_Q_MEDIA_CATALOG_NUMBER</a>  structure.


### -field TrackIsrc

Contains the TrackIsrc code in a <a href="storage.sub_q_track_isrc">SUB_Q_TRACK_ISRC</a> structure. 


## -remarks
The value of the <b>Format </b>member of the CDROM_SUB_Q_DATA_FORMAT structure that is passed as input with IOCTL_CDROM_READ_Q_CHANNEL determines which member of this union is used to return the output data. See <a href="storage.cdrom_sub_q_data_format">CDROM_SUB_Q_DATA_FORMAT</a> for a detailed explanation. 


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
<a href="storage.sub_q_current_position">SUB_Q_CURRENT_POSITION</a>
</dt>
<dt>
<a href="storage.sub_q_media_catalog_number">SUB_Q_MEDIA_CATALOG_NUMBER</a>
</dt>
<dt>
<a href="storage.sub_q_track_isrc">SUB_Q_TRACK_ISRC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SUB_Q_CHANNEL_DATA union%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

