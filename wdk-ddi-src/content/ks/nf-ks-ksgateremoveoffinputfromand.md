---
UID: NF:ks.KsGateRemoveOffInputFromAnd
title: KsGateRemoveOffInputFromAnd function
author: windows-driver-content
description: The KsGateRemoveOffInputFromAnd function removes an existing input that is in the OFF state from an AND gate.
old-location: stream\ksgateremoveoffinputfromand.htm
old-project: stream
ms.assetid: 37f463bb-6b7a-4262-9e4b-3650025acb7c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGateRemoveOffInputFromAnd, KsGateRemoveOffInputFromAnd function [Streaming Media Devices], avfunc_604705b6-08f8-4048-8b29-f89b645f971a.xml, ks/KsGateRemoveOffInputFromAnd, stream.ksgateremoveoffinputfromand
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
-	KsGateRemoveOffInputFromAnd
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsGateRemoveOffInputFromAnd function
The<b> KsGateRemoveOffInputFromAnd</b> function removes an existing input that is in the OFF state from an AND gate.

## Syntax

```
_IRQL_requires_max_(HIGH_LEVEL) void KsGateRemoveOffInputFromAnd(
  PKSGATE AndGate
);
```

## Parameters

`AndGate`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure representing the AND gate from which to remove an OFF input.


## Return Value

None

## Remarks

Removing the last OFF input from the gate results in the gate opening and the transition being propagated to any gates connected to <i>AndGate</i>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

<b>KsGateRemoveOffInputFromAnd</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

<b>KsGateRemoveOffInputFromAnd</b> is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562591">KsGateTurnInputOn</a>. If conceptually removing an existing input to the gate rather than turning it off, a minidriver should call <b>KsGateRemoveOffInputFromAnd</b> instead of <b>KsGateTurnInputOn</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562567">KsGateAddOffInputToAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562569">KsGateAddOnInputToAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562584">KsGateRemoveOnInputFromAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562589">KsGateTurnInputOff</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562591">KsGateTurnInputOn</a>