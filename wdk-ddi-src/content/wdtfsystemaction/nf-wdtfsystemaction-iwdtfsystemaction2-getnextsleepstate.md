---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.GetNextSleepState
title: IWDTFSystemAction2::GetNextSleepState method
author: windows-driver-content
description: Returns the next supported sleep state.
old-location: dtf\iwdtfsystemaction2_getnextsleepstate.htm
old-project: dtf
ms.assetid: B90D7C3D-0370-48A1-90DC-FC14477DA835
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetNextSleepState method [Windows Device Testing Framework], GetNextSleepState method [Windows Device Testing Framework], IWDTFSystemAction2 interface, GetNextSleepState,IWDTFSystemAction2.GetNextSleepState, IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], GetNextSleepState method, IWDTFSystemAction2::GetNextSleepState, Microsoft.WDTF.IWDTFSystemAction2.GetNextSleepState, Microsoft::WDTF::IWDTFSystemAction2::GetNextSleepState, dtf.iwdtfsystemaction2_getnextsleepstate, wdtfsystemaction/IWDTFSystemAction2::GetNextSleepState
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
-	IWDTFSystemAction2.GetNextSleepState
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# GetNextSleepState method
Returns the next supported sleep state.

## Syntax

````
HRESULT GetNextSleepState(
  [out, retval] LONG *pnSleepState
);
````

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

<a href="..\wdtfsystemaction\nn-wdtfsystemaction-iwdtfsystemaction2.md">IWDTFSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSystemAction2::GetNextSleepState method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>