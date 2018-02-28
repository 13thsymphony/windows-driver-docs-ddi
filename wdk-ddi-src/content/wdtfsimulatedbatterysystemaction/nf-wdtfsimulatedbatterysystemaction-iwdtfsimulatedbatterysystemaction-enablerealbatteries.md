---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.EnableRealBatteries
title: IWDTFSimulatedBatterySystemAction::EnableRealBatteries method
author: windows-driver-content
description: Enables real batteries if they are present in the system.
old-location: dtf\iwdtfsimulatedbatterysystemaction_enablerealbatteries.htm
old-project: dtf
ms.assetid: 32748776-fe07-4f7e-bceb-5b554fa8f9f1
ms.author: windowsdriverdev
ms.date: 2/23/2018
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
-	IWDTFSimulatedBatterySystemAction.EnableRealBatteries
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# EnableRealBatteries method
Enables real batteries if they are present in the system.



Use this method to enable real batteries if they are present in the
    system.  If no real batteries are present, this method does nothing. This
    method should be called when disabling the simulated battery in order to return the system to its original state.

## Syntax

````
HRESULT EnableRealBatteries(
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

<a href="..\wdtfsimulatedbatterysystemaction\nn-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction.md">IWDTFSimulatedBatterySystemAction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimulatedBatterySystemAction::EnableRealBatteries method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>