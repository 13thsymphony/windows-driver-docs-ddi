---
UID: NS.DRMK.PKSDRMAUDIOSTREAM_CONTENTID
title: PKSDRMAUDIOSTREAM_CONTENTID
author: windows-driver-content
description: The KSDRMAUDIOSTREAM_CONTENTID structure specifies the DRM content ID and DRM content rights for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request.
old-location: audio\ksdrmaudiostream_contentid.htm
old-project: audio
ms.assetid: d11be514-2a45-407e-884a-66f6f503f57a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSDRMAUDIOSTREAM_CONTENTID, *PKSDRMAUDIOSTREAM_CONTENTID, KSDRMAUDIOSTREAM_CONTENTID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSDRMAUDIOSTREAM_CONTENTID
req.alt-loc: drmk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# PKSDRMAUDIOSTREAM_CONTENTID structure



## -description
The KSDRMAUDIOSTREAM_CONTENTID structure specifies the DRM content ID and DRM content rights for a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request.



## -syntax

````
typedef struct {
  ULONG     ContentId;
  DRMRIGHTS DrmRights;
} KSDRMAUDIOSTREAM_CONTENTID, *PKSDRMAUDIOSTREAM_CONTENTID;
````


## -struct-fields

### -field ContentId

Specifies the DRM content ID. This member identifies a protected KS audio stream.


### -field DrmRights

Specifies the DRM content rights assigned to the stream. This member is a pointer to a <a href="audio.drmrights">DRMRIGHTS</a> structure.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Drmk.h (include Drmk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>
</dt>
<dt>
<a href="audio.drmrights">DRMRIGHTS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDRMAUDIOSTREAM_CONTENTID structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

