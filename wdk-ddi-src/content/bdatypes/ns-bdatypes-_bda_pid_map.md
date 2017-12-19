---
UID: NS.BDATYPES._BDA_PID_MAP
title: _BDA_PID_MAP
author: windows-driver-content
description: The BDA_PID_MAP structure describes a type of data to filter out of the input stream of a packet identifier (PID) filter and then pass to a downstream filter.
old-location: stream\bda_pid_map.htm
old-project: stream
ms.assetid: a5ad0f35-8413-4828-92f8-47544a6e802e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _BDA_PID_MAP, *PBDA_PID_MAP, PBDA_PID_MAP, BDA_PID_MAP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: Bdatypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDA_PID_MAP
req.alt-loc: bdatypes.h
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

# _BDA_PID_MAP structure



## -description
The BDA_PID_MAP structure describes a type of data to filter out of the input stream of a packet identifier (PID) filter and then pass to a downstream filter. This output consists of packets that are identified with PIDs and contain particular media content. 



## -syntax

````
typedef struct _BDA_PID_MAP {
  MEDIA_SAMPLE_CONTENT MediaSampleContent;
  ULONG                ulcPIDs;
  ULONG                aulPIDs[MIN_DIMENSION];
} BDA_PID_MAP, *PBDA_PID_MAP;
````


## -struct-fields

### -field MediaSampleContent

MEDIA_SAMPLE_CONTENT enumerated type value that specifies the type of media content that packets contain. 


### -field ulcPIDs

Number of PIDs in the <b>aulPIDs</b> array. 


### -field aulPIDs

Array of PIDs that identify packets to map to the output of a PID filter. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bdatypes.h (include Bdatypes.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.bda_pid_unmap">BDA_PID_UNMAP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566551">KSPROPSETID_BdaPIDFilter</a>
</dt>
<dt>
<a href="stream.media_sample_content">MEDIA_SAMPLE_CONTENT</a>
</dt>
<dt>
<a href="..\bdatypes\ns-bdatypes-pid_map.md">PID_MAP</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_PID_MAP structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

