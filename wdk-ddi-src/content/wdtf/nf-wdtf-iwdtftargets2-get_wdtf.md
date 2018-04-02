---
UID: NF:wdtf.IWDTFTargets2.get_WDTF
title: IWDTFTargets2::get_WDTF method
author: windows-driver-content
description: Gets the main WDTF aggregation object.
old-location: dtf\iwdtftargets2_wdtf.htm
old-project: dtf
ms.assetid: 1f936c5d-fb1b-4c31-84dc-f246bb0fb453
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFTargets2, IWDTFTargets2 interface [Windows Device Testing Framework], WDTF property, IWDTFTargets2.WDTF, IWDTFTargets2::get_WDTF, Microsoft.WDTF.IWDTFTargets2.WDTF, Microsoft::WDTF::IWDTFTargets2::WDTF, WDTF property [Windows Device Testing Framework], WDTF property [Windows Device Testing Framework], IWDTFTargets2 interface, dtf.iwdtftargets2_wdtf, get_WDTF,IWDTFTargets2.get_WDTF, wdtf/IWDTFTargets2::WDTF, wdtf/IWDTFTargets2::get_WDTF
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
-	IWDTFTargets2.WDTF
-	IWDTFTargets2.get_WDTF
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFTargets2::get_WDTF method
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



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439458">IWDTFTargets2</a>