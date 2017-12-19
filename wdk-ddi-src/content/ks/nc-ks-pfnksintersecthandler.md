---
UID: NC.ks.PFNKSINTERSECTHANDLER
title: PFNKSINTERSECTHANDLER
author: windows-driver-content
description: A streaming minidriver's KStrIntersectHandler routine is called to compare a data range to determine if there is an intersection, and if so, the data format of the intersection.
old-location: stream\kstrintersecthandler.htm
old-project: stream
ms.assetid: ec4ca8b0-5386-4a03-8cf8-46852c168732
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KStrIntersectHandler
req.alt-loc: ks.h
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

# PFNKSINTERSECTHANDLER callback



## -description
A streaming minidriver's <i>KStrIntersectHandler</i> routine is called to compare a data range to determine if there is an intersection, and if so, the data format of the intersection.



## -prototype

````
PFNKSINTERSECTHANDLER KStrIntersectHandler;

NTSTATUS KStrIntersectHandler(
  _In_      PIRP         Irp,
  _In_      PKSP_PIN     Pin,
  _In_      PKSDATARANGE DataRange,
  _Out_opt_ PVOID        Data
)
{ ... }
````


## -parameters

### -param Irp [in]

Specifies the IRP that handles the property request.


### -param Pin [in]

Specifies the specific property being queried and the pin factory identifier that was validated.


### -param DataRange [in]

Specifies the current data range to compare. The data range has been validated as either matching a particular range on the pin or as a wildcard match.


### -param Data [out, optional]

Specifies the data format returned, or the size, in bytes, of the data format.


## -returns
Returns STATUS_SUCCESS if there is a data intersection that fits in the supplied buffer. Otherwise, one of the following values is returned. 
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>For successful size queries. 
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>If the supplied buffer is too small.
<dl>
<dt><b>STATUS_NO_MATCH</b></dt>
</dl>If there is no intersection.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.kspindataintersection">KsPinDataIntersection</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrIntersectHandler routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

