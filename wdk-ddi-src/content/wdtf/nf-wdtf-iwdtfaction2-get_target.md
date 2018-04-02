---
UID: NF:wdtf.IWDTFAction2.get_Target
title: IWDTFAction2::get_Target method
author: windows-driver-content
description: Gets the target to which this action refers.
old-location: dtf\iwdtfaction2_target.htm
old-project: dtf
ms.assetid: 9713c1c8-2bfc-4ac4-82f1-b223d3fe2511
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFAction2, IWDTFAction2 interface [Windows Device Testing Framework], Target property, IWDTFAction2.Target, IWDTFAction2::get_Target, Microsoft.WDTF.IWDTFAction2.Target, Microsoft::WDTF::IWDTFAction2::Target, Target property [Windows Device Testing Framework], Target property [Windows Device Testing Framework], IWDTFAction2 interface, dtf.iwdtfaction2_target, get_Target,IWDTFAction2.get_Target, wdtf/IWDTFAction2::Target, wdtf/IWDTFAction2::get_Target
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
-	IWDTFAction2.Target
-	IWDTFAction2.get_Target
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFAction2::get_Target method
Gets the target to which this action refers.

This property is read-only.

## Syntax

```
HRESULT get_Target(
  IWDTFTarget2 **ppTarget
);
```

## Parameters

`ppTarget`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406311">IWDTFAction2</a>