---
UID: NF:ks.KsGateAddOffInputToAnd
title: KsGateAddOffInputToAnd function
author: windows-driver-content
description: The KsGateAddOffInputToAnd function adds a new input in the OFF state to a given AND gate.
old-location: stream\ksgateaddoffinputtoand.htm
old-project: stream
ms.assetid: 53e03b1d-0995-43cf-945a-22834a9e8240
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGateAddOffInputToAnd, KsGateAddOffInputToAnd function [Streaming Media Devices], avfunc_52efe27b-d77a-490d-beba-3a05b3d5ed83.xml, ks/KsGateAddOffInputToAnd, stream.ksgateaddoffinputtoand
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
-	KsGateAddOffInputToAnd
product: Windows
targetos: Windows
req.typenames: 
---


# KsGateAddOffInputToAnd function
The<b> KsGateAddOffInputToAnd</b> function adds a new input in the OFF state to a given AND gate.

## Syntax

````
void __inline KsGateAddOffInputToAnd(
  _In_ PKSGATE AndGate
);
````

## Parameters

`AndGate`

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure representing the AND gate to which to add a new OFF input.


## Return Value

None

## Remarks

Adding an OFF input to an open AND gate closes the gate and propagates the close down to any attached gates.

This function should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

<b>KsGateAddOffInputToAnd</b> is an inline function call to <a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>. If conceptually adding a new input to a gate, the minidriver should call <b>KsGateAddOffInputToAnd</b> rather than <b>KsGateTurnInputOff</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | Any level |

## See Also

<a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>



<a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>



<a href="..\ks\nf-ks-ksgateaddoninputtoand.md">KsGateAddOnInputToAnd</a>



<a href="..\ks\nf-ks-ksgateremoveoninputfromand.md">KsGateRemoveOnInputFromAnd</a>



<a href="..\ks\nf-ks-ksgateremoveoffinputfromand.md">KsGateRemoveOffInputFromAnd</a>