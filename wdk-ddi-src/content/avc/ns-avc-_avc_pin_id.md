---
UID: NS:avc._AVC_PIN_ID
title: "_AVC_PIN_ID"
author: windows-driver-content
description: The AVC_PIN_ID structure describes a pin on a subunit.
old-location: stream\avc_pin_id.htm
old-project: stream
ms.assetid: 0341b1c4-a050-45f4-b9fc-b28b6a8af75d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PAVC_PIN_ID, AVC_PIN_ID, AVC_PIN_ID structure [Streaming Media Devices], PAVC_PIN_ID, PAVC_PIN_ID structure pointer [Streaming Media Devices], _AVC_PIN_ID, avc/AVC_PIN_ID, avc/PAVC_PIN_ID, avcref_28e8a7a5-a90b-4e1b-ad4c-1a1ccbc405c5.xml, stream.avc_pin_id"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
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
-	avc.h
api_name:
-	AVC_PIN_ID
product: Windows
targetos: Windows
req.typenames: AVC_PIN_ID, *PAVC_PIN_ID
---

# _AVC_PIN_ID structure
The AVC_PIN_ID structure describes a pin on a subunit.

## Syntax
````
typedef struct _AVC_PIN_ID {
  ULONG PinId;
} AVC_PIN_ID, *PAVC_PIN_ID;
````

## Members


`PinId`

Specifies the offset (or ID) of the pin.

## Remarks
This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554148">AVC_FUNCTION_ACQUIRE</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554169">AVC_FUNCTION_RELEASE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554149">AVC_FUNCTION_CLR_CONNECTINFO</a> function codes.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | avc.h (include Avc.h) |

## See Also

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554169">AVC_FUNCTION_RELEASE</a>



<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554148">AVC_FUNCTION_ACQUIRE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554149">AVC_FUNCTION_CLR_CONNECTINFO</a>