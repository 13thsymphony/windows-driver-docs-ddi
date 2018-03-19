---
UID: NS:avc._AVC_PIN_COUNT
title: "_AVC_PIN_COUNT"
author: windows-driver-content
description: The AVC_PIN_COUNT structure specifies the number of pins on an AV/C subunit device.
old-location: stream\avc_pin_count.htm
old-project: stream
ms.assetid: e43557ed-3394-47df-9581-fc3f0c314529
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PAVC_PIN_COUNT, AVC_PIN_COUNT, AVC_PIN_COUNT structure [Streaming Media Devices], PAVC_PIN_COUNT, PAVC_PIN_COUNT structure pointer [Streaming Media Devices], _AVC_PIN_COUNT, avc/AVC_PIN_COUNT, avc/PAVC_PIN_COUNT, avcref_693c28a9-c746-4116-aee7-0de54ce08565.xml, stream.avc_pin_count"
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
-	AVC_PIN_COUNT
product: Windows
targetos: Windows
req.typenames: AVC_PIN_COUNT, *PAVC_PIN_COUNT
---

# _AVC_PIN_COUNT structure
The AVC_PIN_COUNT structure specifies the number of pins on an AV/C subunit device.

## Syntax
````
typedef struct _AVC_PIN_COUNT {
  ULONG PinCount;
} AVC_PIN_COUNT, *PAVC_PIN_COUNT;
````

## Members


`PinCount`

This value is filled in by <i>avc.sys</i> on return from the <b>AVC_FUNCTION_GET_PIN_COUNT</b> function.

## Remarks
This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554158">AVC_FUNCTION_GET_PIN_COUNT</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | avc.h (include Avc.h) |

## See Also

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>



<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554158">AVC_FUNCTION_GET_PIN_COUNT</a>