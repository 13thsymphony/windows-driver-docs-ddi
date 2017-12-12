---
UID: NS.KSMEDIA._TAGKSTOPOLOGY_ENDPOINTIDPAIR
title: _tagKSTOPOLOGY_ENDPOINTIDPAIR
author: windows-driver-content
description: The KSTOPOLOGY_ENDPOINTIDPAIR structure specifies the render and capture endpoint IDs to use for the KSPROPERTY_TELEPHONY_ENDPOINTIDPAIR property.
old-location: audio\kstopology_endpointidpair.htm
old-project: audio
ms.assetid: 556B56A6-1EF4-406B-A9FB-901C0CF24BC0
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _tagKSTOPOLOGY_ENDPOINTIDPAIR, KSTOPOLOGY_ENDPOINTIDPAIR, *PKSTOPOLOGY_ENDPOINTIDPAIR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSTOPOLOGY_ENDPOINTIDPAIR
req.alt-loc: ksmedia.h
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

# _tagKSTOPOLOGY_ENDPOINTIDPAIR structure



## -description
The <b>KSTOPOLOGY_ENDPOINTIDPAIR</b> structure specifies the render and capture endpoint IDs to use for the <a href="https://msdn.microsoft.com/library/windows/hardware/mt169874">KSPROPERTY_TELEPHONY_ENDPOINTIDPAIR</a> property.



## -syntax

````
typedef struct _tagKSTOPOLOGY_ENDPOINTIDPAIR {
  KSTOPOLOGY_ENDPOINTID RenderEndpoint;
  KSTOPOLOGY_ENDPOINTID CaptureEndpoint;
} KSTOPOLOGY_ENDPOINTIDPAIR, *PKSTOPOLOGY_ENDPOINTIDPAIR;
````


## -struct-fields

### -field RenderEndpoint

Specifies the render endpoint ID.


### -field CaptureEndpoint

Specifies the capture endpoint ID. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Client

</th>
<td width="70%">
Windows 10 Mobile

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.kstopology_endpointid">KSTOPOLOGY_ENDPOINTID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSTOPOLOGY_ENDPOINTIDPAIR structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

