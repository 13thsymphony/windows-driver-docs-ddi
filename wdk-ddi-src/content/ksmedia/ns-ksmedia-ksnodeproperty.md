---
UID: NS:ksmedia.KSNODEPROPERTY
title: KSNODEPROPERTY
author: windows-driver-content
description: The KSNODEPROPERTY structure specifies a node and a property of that node.
old-location: audio\ksnodeproperty.htm
old-project: audio
ms.assetid: bbcf7597-217a-499b-b0f2-deef1e85becc
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSNODEPROPERTY, KSNODEPROPERTY, KSNODEPROPERTY structure [Audio Devices], PKSNODEPROPERTY, PKSNODEPROPERTY structure pointer [Audio Devices], aud-prop_7d1e6907-77f6-445d-ba5d-b94037b234f3.xml, audio.ksnodeproperty, ksmedia/KSNODEPROPERTY, ksmedia/PKSNODEPROPERTY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSNODEPROPERTY
product: Windows
targetos: Windows
req.typenames: KSNODEPROPERTY, *PKSNODEPROPERTY
---

# KSNODEPROPERTY structure
The KSNODEPROPERTY structure specifies a node and a property of that node.

## Syntax
````
typedef struct {
  KSPROPERTY Property;
  ULONG      NodeId;
  ULONG      Reserved;
} KSNODEPROPERTY, *PKSNODEPROPERTY;
````

## Members


`Property`

Specifies the property to get or set. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>.

`NodeId`

Specifies the node ID. This member identifies the target node for the property request.

`Reserved`

Reserved for internal use by operating system. Do not use.

## Remarks
This structure is identical to <a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a>.

See the discussion of the KSNODEPROPERTY structure in <a href="https://msdn.microsoft.com/dcfd139c-fca3-4068-8324-aa2c952dbc1f">Audio Property Requests</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a>