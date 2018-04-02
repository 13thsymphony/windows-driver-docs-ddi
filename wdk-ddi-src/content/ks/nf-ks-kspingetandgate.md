---
UID: NF:ks.KsPinGetAndGate
title: KsPinGetAndGate function
author: windows-driver-content
description: The KsPinGetAndGate function returns the processing control gate for Pin.
old-location: stream\kspingetandgate.htm
old-project: stream
ms.assetid: abd4da69-c0c3-442f-af58-e77362c637da
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinGetAndGate, KsPinGetAndGate function [Streaming Media Devices], avfunc_a4159ef9-1a69-4716-96ce-4fabd1ee6218.xml, ks/KsPinGetAndGate, stream.kspingetandgate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsPinGetAndGate
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsPinGetAndGate function
The<b> KsPinGetAndGate</b> function returns the processing control gate for <i>Pin</i>.

## Syntax

```
KSDDKAPI PKSGATE KsPinGetAndGate(
  PKSPIN Pin
);
```

## Parameters

`Pin`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> for which to return the processing control gate.


## Return Value

Returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> representing the processing control gate for <i>Pin</i>.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562542">KsFilterGetAndGate</a>