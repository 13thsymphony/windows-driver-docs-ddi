---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.GetFirstSleepState
title: IWDTFSystemAction2::GetFirstSleepState method
author: windows-driver-content
description: Returns the first supported sleep state.
old-location: dtf\iwdtfsystemaction2_getfirstsleepstate.htm
old-project: dtf
ms.assetid: EE298195-5EAA-40E4-84F5-9B169F55DBF1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GetFirstSleepState method [Windows Device Testing Framework], GetFirstSleepState method [Windows Device Testing Framework], IWDTFSystemAction2 interface, GetFirstSleepState,IWDTFSystemAction2.GetFirstSleepState, IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], GetFirstSleepState method, IWDTFSystemAction2::GetFirstSleepState, Microsoft.WDTF.IWDTFSystemAction2.GetFirstSleepState, Microsoft::WDTF::IWDTFSystemAction2::GetFirstSleepState, dtf.iwdtfsystemaction2_getfirstsleepstate, wdtfsystemaction/IWDTFSystemAction2::GetFirstSleepState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfsystemaction.h
req.include-header: 
req.target-type: Desktop
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
-	IWDTFSystemAction2.GetFirstSleepState
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFSystemAction2::GetFirstSleepState method
Returns the first supported sleep state.

## Syntax

```
HRESULT GetFirstSleepState(
  LONG *pnSleepState
);
```

## Parameters

`pnSleepState`

The sleep state.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfsystemaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439302">IWDTFSystemAction2</a>