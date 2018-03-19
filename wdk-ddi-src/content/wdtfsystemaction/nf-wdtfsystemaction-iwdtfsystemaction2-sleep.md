---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.Sleep
title: IWDTFSystemAction2::Sleep method
author: windows-driver-content
description: Puts the system into the desired sleep state.
old-location: dtf\iwdtfsystemaction2_sleep.htm
old-project: dtf
ms.assetid: 4DC3E14E-6FC3-49C1-AB22-779D0E8CA68D
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], Sleep method, IWDTFSystemAction2::Sleep, Microsoft.WDTF.IWDTFSystemAction2.Sleep, Microsoft::WDTF::IWDTFSystemAction2::Sleep, Sleep method [Windows Device Testing Framework], Sleep method [Windows Device Testing Framework], IWDTFSystemAction2 interface, Sleep,IWDTFSystemAction2.Sleep, dtf.iwdtfsystemaction2_sleep, wdtfsystemaction/IWDTFSystemAction2::Sleep
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
-	IWDTFSystemAction2.Sleep
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# Sleep method
Puts the system into the desired sleep state.

## Syntax

````
HRESULT Sleep(
  [in] LONG nSleepState
);
````

## Parameters

`nSleepState`

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

<a href="..\wdtfsystemaction\nn-wdtfsystemaction-iwdtfsystemaction2.md">IWDTFSystemAction2</a>