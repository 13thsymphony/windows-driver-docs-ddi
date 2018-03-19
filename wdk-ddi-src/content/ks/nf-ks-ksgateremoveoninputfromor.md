---
UID: NF:ks.KsGateRemoveOnInputFromOr
title: KsGateRemoveOnInputFromOr function
author: windows-driver-content
description: The KsGateRemoveOnInputFromOr function removes an existing input that is in the ON state from an OR gate.
old-location: stream\ksgateremoveoninputfromor.htm
old-project: stream
ms.assetid: e7226684-afbf-46e1-aeb2-6b0c60c12680
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGateRemoveOnInputFromOr, KsGateRemoveOnInputFromOr function [Streaming Media Devices], avfunc_6f131d80-de01-44e6-a17d-eb7f9b0b968f.xml, ks/KsGateRemoveOnInputFromOr, stream.ksgateremoveoninputfromor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsGateRemoveOnInputFromOr
product: Windows
targetos: Windows
req.typenames: 
---


# KsGateRemoveOnInputFromOr function
The<b> KsGateRemoveOnInputFromOr </b>function removes an existing input that is in the ON state from an OR gate.

## Syntax

````
void __inline KsGateRemoveOnInputFromOr(
  _In_ PKSGATE OrGate
);
````

## Parameters

`OrGate`

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure representing the OR gate from which to remove an ON input.


## Return Value

None

## Remarks

Removing the last ON input from a given OR gate results in the gate closing and the transition being propagated to any gates connected to <i>OrGate</i>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

<b>KsGateRemoveOnInputFromOr</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

This call is an inline function call to <a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>. If conceptually removing an existing input to a gate, a minidriver should call <b>KsGateRemoveOnInputFromOr</b> rather than <b>KsGateTurnInputOff</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | Any level |

## See Also

<a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>



<a href="..\ks\nf-ks-ksgateremoveoffinputfromor.md">KsGateRemoveOffInputFromOr</a>



<a href="..\ks\nf-ks-ksgateaddoffinputtoor.md">KsGateAddOffInputToOr</a>



<a href="..\ks\nf-ks-ksgateaddoninputtoor.md">KsGateAddOnInputToOr</a>



<a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>