---
UID: NF:wdtf.IWDTFTarget2.get_WDTF
title: IWDTFTarget2::get_WDTF method
author: windows-driver-content
description: Gets the main WDTF aggregation object.
old-location: dtf\iwdtftarget2_wdtf.htm
old-project: dtf
ms.assetid: ef3025bf-e33d-47ae-832d-1b32d33cdca3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], WDTF property, IWDTFTarget2.WDTF, IWDTFTarget2::get_WDTF, Microsoft.WDTF.IWDTFTarget2.WDTF, Microsoft::WDTF::IWDTFTarget2::WDTF, WDTF property [Windows Device Testing Framework], WDTF property [Windows Device Testing Framework], IWDTFTarget2 interface, dtf.iwdtftarget2_wdtf, get_WDTF,IWDTFTarget2.get_WDTF, wdtf/IWDTFTarget2::WDTF, wdtf/IWDTFTarget2::get_WDTF
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
-	IWDTFTarget2.WDTF
-	IWDTFTarget2.get_WDTF
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFTarget2::get_WDTF method
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



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a>