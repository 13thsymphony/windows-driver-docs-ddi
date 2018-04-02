---
UID: NF:wdtf.IWDTFSystemDepot2.get_WDTF
title: IWDTFSystemDepot2::get_WDTF method
author: windows-driver-content
description: Gets the main WDTF aggregation object.
old-location: dtf\iwdtfsystemdepot2_wdtf.htm
old-project: dtf
ms.assetid: e742b493-64ee-4311-b6f0-512b44e776f4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFSystemDepot2, IWDTFSystemDepot2 interface [Windows Device Testing Framework], WDTF property, IWDTFSystemDepot2.WDTF, IWDTFSystemDepot2::get_WDTF, Microsoft.WDTF.IWDTFSystemDepot2.WDTF, Microsoft::WDTF::IWDTFSystemDepot2::WDTF, WDTF property [Windows Device Testing Framework], WDTF property [Windows Device Testing Framework], IWDTFSystemDepot2 interface, dtf.iwdtfsystemdepot2_wdtf, get_WDTF,IWDTFSystemDepot2.get_WDTF, wdtf/IWDTFSystemDepot2::WDTF, wdtf/IWDTFSystemDepot2::get_WDTF
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
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
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFSystemDepot2.WDTF
-	IWDTFSystemDepot2.get_WDTF
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFSystemDepot2::get_WDTF method
Gets the main WDTF aggregation object.

This property is read-only.

## Syntax

```
HRESULT get_WDTF(
  IWDTF2 **ppWDTF
);
```

## Parameters

`ppWDTF`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406300">IWDTF2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439331">IWDTFSystemDepot2</a>