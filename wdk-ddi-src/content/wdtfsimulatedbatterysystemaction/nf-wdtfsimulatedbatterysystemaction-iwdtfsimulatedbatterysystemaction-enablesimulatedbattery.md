---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.EnableSimulatedBattery
title: IWDTFSimulatedBatterySystemAction::EnableSimulatedBattery method
author: windows-driver-content
description: Enables the simulated battery.
old-location: dtf\iwdtfsimulatedbatterysystemaction_enablesimulatedbattery.htm
old-project: dtf
ms.assetid: c9ca8bb4-2a05-4934-b589-41fba8092b1b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EnableSimulatedBattery method [Windows Device Testing Framework], EnableSimulatedBattery method [Windows Device Testing Framework], IWDTFSimulatedBatterySystemAction interface, EnableSimulatedBattery,IWDTFSimulatedBatterySystemAction.EnableSimulatedBattery, IWDTFSimulatedBatterySystemAction, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework], EnableSimulatedBattery method, IWDTFSimulatedBatterySystemAction::EnableSimulatedBattery, dtf.iwdtfsimulatedbatterysystemaction_enablesimulatedbattery, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::EnableSimulatedBattery
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
req.lib: wdtfsimulatedbatterysystemaction.h
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
-	IWDTFSimulatedBatterySystemAction.EnableSimulatedBattery
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# EnableSimulatedBattery method
Enables the simulated battery.



 Use this method to enable the simulated battery (installs simulated
    battery device).  This does not guarantee the ability to simulate DC by
    itself, the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265161">IWDTFSimulatedBatterySystemAction::DisableRealBatteries</a> method must also be called in order to guarantee a real battery doesn't interfere with the simulation.

## Syntax

````
HRESULT EnableSimulatedBattery(
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
| **Library** | wdtfsimulatedbatterysystemaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265161">IWDTFSimulatedBatterySystemAction::DisableRealBatteries</a>



<a href="..\wdtfsimulatedbatterysystemaction\nn-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction.md">IWDTFSimulatedBatterySystemAction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimulatedBatterySystemAction::EnableSimulatedBattery method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>