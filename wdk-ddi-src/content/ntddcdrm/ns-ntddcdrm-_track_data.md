---
UID: NS.NTDDCDRM._TRACK_DATA
title: _TRACK_DATA
author: windows-driver-content
description: Track descriptor is used in conjunction with CDROM_TOC and CDROM_TOC_SESSION_DATA.
old-location: storage\track_data.htm
old-project: storage
ms.assetid: f412ff4e-6c65-40f8-9747-dc5059e588f6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _TRACK_DATA, PTRACK_DATA, TRACK_DATA, *PTRACK_DATA
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
req.alt-api: TRACK_DATA
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

# _TRACK_DATA structure



## -description
Track descriptor is used in conjunction with <a href="storage.cdrom_toc">CDROM_TOC</a> and <a href="storage.cdrom_toc_session_data">CDROM_TOC_SESSION_DATA</a>. 



## -syntax

````
typedef struct _TRACK_DATA {
  UCHAR Reserved;
  UCHAR Control  :4;
  UCHAR Adr  :4;
  UCHAR TrackNumber;
  UCHAR Reserved1;
  UCHAR Address[4];
} TRACK_DATA, *PTRACK_DATA;
````


## -struct-fields

### -field Reserved

Reserved. 


### -field Control

Indicates the attributes of the track. For information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS). 


### -field Adr

Indicates the type of information encoded in the Q subchannel of the track where this table of contents entry was found. For information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS). 


### -field TrackNumber

Indicates the number of the track. 


### -field Reserved1

Reserved. 


### -field Address

Indicates the starting address of the track. 


## -remarks
This structure contains table of contents information for a track.


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
<a href="storage.cdrom_toc">CDROM_TOC</a>
</dt>
<dt>
<a href="storage.cdrom_toc_session_data">CDROM_TOC_SESSION_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TRACK_DATA structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

