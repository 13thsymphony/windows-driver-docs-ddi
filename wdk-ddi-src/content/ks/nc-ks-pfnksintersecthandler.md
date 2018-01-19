---
UID : NC:ks.PFNKSINTERSECTHANDLER
title : PFNKSINTERSECTHANDLER
author : windows-driver-content
description : A streaming minidriver's KStrIntersectHandler routine is called to compare a data range to determine if there is an intersection, and if so, the data format of the intersection.
old-location : stream\kstrintersecthandler.htm
old-project : stream
ms.assetid : ec4ca8b0-5386-4a03-8cf8-46852c168732
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : NpdBrokerUninitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ks.h
req.include-header : Ks.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KStrIntersectHandler
req.alt-loc : ks.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : KEYWORDSELECTOR
---


# PFNKSINTERSECTHANDLER callback function
A streaming minidriver's <i>KStrIntersectHandler</i> routine is called to compare a data range to determine if there is an intersection, and if so, the data format of the intersection.

## Syntax

```
PFNKSINTERSECTHANDLER Pfnksintersecthandler;

NTSTATUS Pfnksintersecthandler(
  PIRP Irp,
  PKSP_PIN Pin,
  PKSDATARANGE DataRange,
  PVOID Data
)
{...}
```

## Parameters

`Irp`

Specifies the IRP that handles the property request.

`Pin`

Specifies the specific property being queried and the pin factory identifier that was validated.

`DataRange`

Specifies the current data range to compare. The data range has been validated as either matching a particular range on the pin or as a wildcard match.

`Data`

Specifies the data format returned, or the size, in bytes, of the data format.


## Return Value

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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\nf-ks-kspindataintersection.md">KsPinDataIntersection</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSINTERSECTHANDLER routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>