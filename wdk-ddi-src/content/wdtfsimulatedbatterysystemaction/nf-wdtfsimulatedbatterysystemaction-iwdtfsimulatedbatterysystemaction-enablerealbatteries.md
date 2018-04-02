---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.EnableRealBatteries
title: IWDTFSimulatedBatterySystemAction::EnableRealBatteries method
author: windows-driver-content
description: Enables real batteries if they are present in the system.
old-location: dtf\iwdtfsimulatedbatterysystemaction_enablerealbatteries.htm
old-project: dtf
ms.assetid: 32748776-fe07-4f7e-bceb-5b554fa8f9f1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EnableRealBatteries method [Windows Device Testing Framework], EnableRealBatteries method [Windows Device Testing Framework], IWDTFSimulatedBatterySystemAction interface, EnableRealBatteries,IWDTFSimulatedBatterySystemAction.EnableRealBatteries, IWDTFSimulatedBatterySystemAction, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework], EnableRealBatteries method, IWDTFSimulatedBatterySystemAction::EnableRealBatteries, dtf.iwdtfsimulatedbatterysystemaction_enablerealbatteries, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::EnableRealBatteries
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfsimulatedbatterysystemaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFSimulatedBatterySystemAction.idl
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
-	COM
api_location:
-	wdtfsimulatedbatterysystemaction.h
api_name:
-	IWDTFSimulatedBatterySystemAction.EnableRealBatteries
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFSimulatedBatterySystemAction::EnableRealBatteries method
Enables real batteries if they are present in the system.



Use this method to enable real batteries if they are present in the
    system.  If no real batteries are present, this method does nothing. This
    method should be called when disabling the simulated battery in order to return the system to its original state.

## Syntax

```
HRESULT EnableRealBatteries(
  VARIANT_BOOL *pbSuccess
);
```

## Parameters

`pbSuccess`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | wdtfsimulatedbatterysystemaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265160">IWDTFSimulatedBatterySystemAction</a>