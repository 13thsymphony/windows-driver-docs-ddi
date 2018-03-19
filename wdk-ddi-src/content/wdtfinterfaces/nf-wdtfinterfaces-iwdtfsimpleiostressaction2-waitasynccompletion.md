---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.WaitAsyncCompletion
title: IWDTFSimpleIOStressAction2::WaitAsyncCompletion method
author: windows-driver-content
description: Waits for the completion of any of the asynchronous events.
old-location: dtf\iwdtfsimpleiostressaction2_waitasynccompletion.htm
old-project: dtf
ms.assetid: 7aaf56cf-ba31-495b-9f54-35e9238f188a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSimpleIOStressAction2, IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework], WaitAsyncCompletion method, IWDTFSimpleIOStressAction2::WaitAsyncCompletion, Microsoft.WDTF.IWDTFSimpleIOStressAction2.WaitAsyncCompletion, Microsoft::WDTF::IWDTFSimpleIOStressAction2::WaitAsyncCompletion, WaitAsyncCompletion method [Windows Device Testing Framework], WaitAsyncCompletion method [Windows Device Testing Framework], IWDTFSimpleIOStressAction2 interface, WaitAsyncCompletion,IWDTFSimpleIOStressAction2.WaitAsyncCompletion, dtf.iwdtfsimpleiostressaction2_waitasynccompletion, wdtfinterfaces/IWDTFSimpleIOStressAction2::WaitAsyncCompletion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfinterfaces.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFInterfaces.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFInterfaces.Interop.dll
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
-	WDTFInterfaces.Interop.dll
api_name:
-	IWDTFSimpleIOStressAction2.WaitAsyncCompletion
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# WaitAsyncCompletion method
Waits for the completion of any of the asynchronous events.

## Syntax

````
HRESULT WaitAsyncCompletion(
  [out, retval] VARIANT_BOOL *pResult
);
````

## Parameters

`pResult`

True if the last asynchronous event succeeded; otherwise, false.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfinterfaces.h |

## See Also

<a href="..\wdtfinterfaces\nn-wdtfinterfaces-iwdtfsimpleiostressaction2.md">IWDTFSimpleIOStressAction2</a>