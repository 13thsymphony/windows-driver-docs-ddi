---
UID: NS.AVCSTRM._CIP_HDR2_MPEGTS
title: _CIP_HDR2_MPEGTS
author: windows-driver-content
description: The CIP_HDR2_MPEGTS structure describes the second quadlet of a CIP header pair for an MPEGTS format stream.
old-location: stream\cip_hdr2_mpegts.htm
old-project: stream
ms.assetid: e1f46926-8c2b-46ff-9adb-5332fba17e3b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _CIP_HDR2_MPEGTS, *PCIP_HDR2_MPEGTS, CIP_HDR2_MPEGTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CIP_HDR2_MPEGTS
req.alt-loc: avcstrm.h
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

# _CIP_HDR2_MPEGTS structure



## -description
The CIP_HDR2_MPEGTS structure describes the second quadlet of a CIP header pair for an MPEGTS format stream.



## -syntax

````
typedef struct _CIP_HDR2_MPEGTS {
  ULONG TSF  :1;
  ULONG RSV23bit  :23;
  ULONG FMT  :6;
  ULONG Bit10  :2;
} CIP_HDR2_MPEGTS, *PCIP_HDR2_MPEGTS;
````


## -struct-fields

### -field TSF

Time-shift flag. This is not used for opening a stream.


### -field RSV23bit

Reserved bits. This must be 0. Do not use this.


### -field FMT

CIP format. For example, 000000 = DV and 100000 = MPEGTS.


### -field Bit10

Must be set to 1:0


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Avcstrm.h (include Avcstrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.cip_hdr1">CIP_HDR1</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20CIP_HDR2_MPEGTS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

