---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.Start
title: IWDTFSimpleIOStressAction2::Start method
author: windows-driver-content
description: Opens the device.
old-location: dtf\iwdtfsimpleiostressaction2_start.htm
old-project: dtf
ms.assetid: 4f25224b-5d8c-4d9d-8350-d84b3b75d780
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFSimpleIOStressAction2, IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework], Start method, IWDTFSimpleIOStressAction2::Start, Microsoft.WDTF.IWDTFSimpleIOStressAction2.Start, Microsoft::WDTF::IWDTFSimpleIOStressAction2::Start, Start method [Windows Device Testing Framework], Start method [Windows Device Testing Framework], IWDTFSimpleIOStressAction2 interface, Start,IWDTFSimpleIOStressAction2.Start, dtf.iwdtfsimpleiostressaction2_start, wdtfinterfaces/IWDTFSimpleIOStressAction2::Start
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
-	IWDTFSimpleIOStressAction2.Start
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFSimpleIOStressAction2::Start method
Opens the device.

## Syntax

```
HRESULT Start(
  VARIANT_BOOL *pResult
);
```

## Parameters

`pResult`

True if the device opens; otherwise, false.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfinterfaces.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451157">IWDTFSimpleIOStressAction2</a>