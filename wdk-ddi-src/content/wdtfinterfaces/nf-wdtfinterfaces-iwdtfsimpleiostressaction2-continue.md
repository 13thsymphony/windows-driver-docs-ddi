---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.Continue
title: IWDTFSimpleIOStressAction2::Continue method
author: windows-driver-content
description: Continues the I/O.
old-location: dtf\iwdtfsimpleiostressaction2_continue.htm
old-project: dtf
ms.assetid: 5625c4af-329d-4b16-9d5d-0ca962a7abff
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: Continue method [Windows Device Testing Framework], Continue method [Windows Device Testing Framework], IWDTFSimpleIOStressAction2 interface, Continue,IWDTFSimpleIOStressAction2.Continue, IWDTFSimpleIOStressAction2, IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework], Continue method, IWDTFSimpleIOStressAction2::Continue, Microsoft.WDTF.IWDTFSimpleIOStressAction2.Continue, Microsoft::WDTF::IWDTFSimpleIOStressAction2::Continue, dtf.iwdtfsimpleiostressaction2_continue, wdtfinterfaces/IWDTFSimpleIOStressAction2::Continue
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
-	IWDTFSimpleIOStressAction2.Continue
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# Continue method
Continues the I/O.

## Syntax

````
HRESULT Continue(
  [out, retval] VARIANT_BOOL *pbResult
);
````

## Parameters

`pResult`




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