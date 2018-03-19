---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.DisableSimulatedBattery
title: IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery method
author: windows-driver-content
description: Disables the simulated battery.
old-location: dtf\iwdtfsimulatedbatterysystemaction_disablesimulatedbattery.htm
old-project: dtf
ms.assetid: 52ddeb83-8ac3-4e9d-84d8-dddfcc404b6e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DisableSimulatedBattery method [Windows Device Testing Framework], DisableSimulatedBattery method [Windows Device Testing Framework], IWDTFSimulatedBatterySystemAction interface, DisableSimulatedBattery,IWDTFSimulatedBatterySystemAction.DisableSimulatedBattery, IWDTFSimulatedBatterySystemAction, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework], DisableSimulatedBattery method, IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery, dtf.iwdtfsimulatedbatterysystemaction_disablesimulatedbattery, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery
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
-	IWDTFSimulatedBatterySystemAction.DisableSimulatedBattery
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# DisableSimulatedBattery method
Disables the simulated battery.



Use this method is used to disable the simulated battery (uninstalls simulated
    battery device).  This does not restore the system to its original state, the <a href="https://msdn.microsoft.com/32748776-fe07-4f7e-bceb-5b554fa8f9f1">WDTFSimulatedBatterySystemAction::EnableRealBatteries</a> method must also be called.

## Syntax

````
HRESULT DisableSimulatedBattery(
  [out, retval] VARIANT_BOOL *pbSuccess
);
````

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

<a href="https://msdn.microsoft.com/32748776-fe07-4f7e-bceb-5b554fa8f9f1">WDTFSimulatedBatterySystemAction::EnableRealBatteries</a>



<a href="..\wdtfsimulatedbatterysystemaction\nn-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction.md">IWDTFSimulatedBatterySystemAction</a>