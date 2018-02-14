---
UID: NS:ks.KSP_TIMEFORMAT
title: KSP_TIMEFORMAT
author: windows-driver-content
description: The KSP_TIMEFORMAT structure corresponds to KSPROPERTY_MEDIASEEKING_CONVERTTIMEFORMAT.
old-location: stream\ksp_timeformat.htm
old-project: stream
ms.assetid: 18ce5fc5-927c-4261-8966-bb12849b95c9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks-struct_086a975b-f249-44e9-b1fa-4a945509722e.xml, PKSP_TIMEFORMAT structure pointer [Streaming Media Devices], *PKSP_TIMEFORMAT, ks/KSP_TIMEFORMAT, stream.ksp_timeformat, ks/PKSP_TIMEFORMAT, PKSP_TIMEFORMAT, KSP_TIMEFORMAT, KSP_TIMEFORMAT structure [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSP_TIMEFORMAT
product: Windows
targetos: Windows
req.typenames: KSP_TIMEFORMAT, *PKSP_TIMEFORMAT
---

# KSP_TIMEFORMAT structure
The KSP_TIMEFORMAT structure corresponds to <a href="https://msdn.microsoft.com/library/windows/hardware/ff565181">KSPROPERTY_MEDIASEEKING_CONVERTTIMEFORMAT</a>.

## Syntax
````
typedef struct {
  KSPROPERTY Property;
  GUID       SourceFormat;
  GUID       TargetFormat;
  LONGLONG   Time;
} KSP_TIMEFORMAT, *PKSP_TIMEFORMAT;
````

## Members


`Property`

Specifies a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure.

`SourceFormat`

Pointer to a GUID that specifies the format to convert. If <b>NULL</b>, the current format is used.

`TargetFormat`

Pointer to a GUID that specifies the target format. If <b>NULL</b>, the current format is used.

`Time`

Specifies the time value to convert.

## Remarks
The fields of the structure correspond one to one with DirectShow's IMediaSeeking::ConvertTimeFormat.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565181">KSPROPERTY_MEDIASEEKING_CONVERTTIMEFORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSP_TIMEFORMAT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>