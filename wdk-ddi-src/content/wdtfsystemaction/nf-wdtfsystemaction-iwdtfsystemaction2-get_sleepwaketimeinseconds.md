---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.get_SleepWakeTimeInSeconds
title: IWDTFSystemAction2::get_SleepWakeTimeInSeconds method
author: windows-driver-content
description: Gets or sets the time in seconds when the system will wake from the sleep state.
old-location: dtf\iwdtfsystemaction2_sleepwaketimeinseconds.htm
old-project: dtf
ms.assetid: 90b9742d-966b-4502-92ec-670c663d9a76
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], SleepWakeTimeInSeconds property, IWDTFSystemAction2.SleepWakeTimeInSeconds, IWDTFSystemAction2::get_SleepWakeTimeInSeconds, IWDTFSystemAction2::put_SleepWakeTimeInSeconds, Microsoft.WDTF.IWDTFSystemAction2.SleepWakeTimeInSeconds, Microsoft::WDTF::IWDTFSystemAction2::SleepWakeTimeInSeconds, SleepWakeTimeInSeconds property [Windows Device Testing Framework], SleepWakeTimeInSeconds property [Windows Device Testing Framework], IWDTFSystemAction2 interface, dtf.iwdtfsystemaction2_sleepwaketimeinseconds, get_SleepWakeTimeInSeconds,IWDTFSystemAction2.get_SleepWakeTimeInSeconds, wdtfsystemaction/IWDTFSystemAction2::SleepWakeTimeInSeconds, wdtfsystemaction/IWDTFSystemAction2::get_SleepWakeTimeInSeconds, wdtfsystemaction/IWDTFSystemAction2::put_SleepWakeTimeInSeconds
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfsystemaction.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFSystemAction.Interop.dll
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
-	WDTFSystemAction.Interop.dll
api_name:
-	IWDTFSystemAction2.SleepWakeTimeInSeconds
-	IWDTFSystemAction2.get_SleepWakeTimeInSeconds
-	IWDTFSystemAction2.put_SleepWakeTimeInSeconds
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFSystemAction2::get_SleepWakeTimeInSeconds method
Gets or sets the time in seconds when the system will wake from the sleep state.

This property is read/write.

## Syntax

```
HRESULT get_SleepWakeTimeInSeconds(
  LONG *pnWakeTimeInSeconds
);
```

## Parameters

`pnWakeTimeInSeconds`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtfsystemaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439302">IWDTFSystemAction2</a>