---
UID: NF:ks.KsPinRegisterPowerCallbacks
title: KsPinRegisterPowerCallbacks function
author: windows-driver-content
description: The KsPinRegisterPowerCallbacks function registers power management callbacks for Pin.
old-location: stream\kspinregisterpowercallbacks.htm
old-project: stream
ms.assetid: e498a907-8d20-4d00-9411-8e82030af223
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinRegisterPowerCallbacks, KsPinRegisterPowerCallbacks function [Streaming Media Devices], avfunc_2e133cdb-6afa-47a7-8d3b-8293b63428b5.xml, ks/KsPinRegisterPowerCallbacks, stream.kspinregisterpowercallbacks
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsPinRegisterPowerCallbacks
product: Windows
targetos: Windows
req.typenames: 
---


# KsPinRegisterPowerCallbacks function
The<b> KsPinRegisterPowerCallbacks </b>function registers power management callbacks for <i>Pin</i>.

## Syntax

```
void KsPinRegisterPowerCallbacks(
  PKSPIN        Pin,
  PFNKSPINPOWER Sleep,
  PFNKSPINPOWER Wake
);
```

## Parameters

`Pin`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure for which to register power callbacks. Note that the pin must actually process (be pin-centric) in order to receive power notification messages.

`Sleep`

This parameter supplies the address of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556345">AVStrMiniPinPower</a>  function that handles sleep requests for the device. Optional.

`Wake`

This parameter supplies the address of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556345">AVStrMiniPinPower</a>  function that handles wake requests for the device. Optional.


## Return Value

None

## Remarks

<div class="alert"><b>Warning</b>  <i>Do not attempt to obtain the filter control mutex</i> from within either the Sleep or Wake callback, or deadlock may occur. For more information about mutexes, read <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.</div>
<div> </div>
At least one of the callbacks must be specified when calling <b>KsPinRegisterPowerCallbacks</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556345">AVStrMiniPinPower</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562550">KsFilterRegisterPowerCallbacks</a>