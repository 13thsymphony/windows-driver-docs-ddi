---
UID: NS:dxva._DXVA_Frequency
title: "_DXVA_Frequency"
author: windows-driver-content
description: The DXVA_Frequency structure is sent by the host decoder to the driver to specify the video frame rate, in Hz. For example, NTSC TV is 60000 over 1001.
old-location: display\dxva_frequency.htm
old-project: display
ms.assetid: 4e7d9746-7dae-4f53-9bf8-e0acc807306a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA_Frequency structure [Display Devices], display.dxva_frequency, dxva/DXVA_Frequency, dxvaref_a36a3edd-8f65-4d6d-85d0-360e0f03e978.xml, _DXVA_Frequency, DXVA_Frequency
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
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
-	dxva.h
apiname:
-	DXVA_Frequency
product: Windows
targetos: Windows
req.typenames: DXVA_Frequency
---

# _DXVA_Frequency structure
The DXVA_Frequency structure is sent by the host decoder to the driver to specify the video frame rate, in Hz. For example, NTSC TV is 60000 over 1001.

## Syntax
````
typedef struct _DXVA_Frequency {
  DWORD Numerator;
  DWORD Denominator;
} DXVA_Frequency;
````

## Members


`Denominator`

Specifies the denominator of the frequency fraction.

`Numerator`

Specifies the numerator of the frequency fraction.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dxva.h (include Dxva.h) |