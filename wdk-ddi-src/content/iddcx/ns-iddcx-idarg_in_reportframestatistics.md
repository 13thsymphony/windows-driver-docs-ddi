---
UID: NS:iddcx.IDARG_IN_REPORTFRAMESTATISTICS
title: IDARG_IN_REPORTFRAMESTATISTICS
author: windows-driver-content
description: Gives information about frame statistics.
old-location: display\idarg_in_reportframestatistics.htm
old-project: display
ms.assetid: 3d3e0dca-bb05-4e5c-aa4a-76bb178f60bf
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDARG_IN_REPORTFRAMESTATISTICS,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDARG_IN_REPORTFRAMESTATISTICS
req.alt-loc: iddcx.h
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
req.typenames: 
---

# IDARG_IN_REPORTFRAMESTATISTICS structure



## -description

                 Gives information about frame statistics.



## -syntax

````
typedef struct IDARG_IN_REPORTFRAMESTATISTICS {
  IDDCX_FRAME_STATISTICS FrameStatistics;
} IDARG_IN_REPORTFRAMESTATISTICS, *IDARG_IN_REPORTFRAMESTATISTICS;
````


## -struct-fields

### -field FrameStatistics


                     [in] Frame statics being reported.
                 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>