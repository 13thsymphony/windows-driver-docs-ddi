---
UID: NF:wdtf.IWDTFAction2.GetStatus
title: IWDTFAction2::GetStatus method
author: windows-driver-content
description: Returns the status code for the last operation.
old-location: dtf\iwdtfaction2_getstatus.htm
old-project: dtf
ms.assetid: 39e5bfb8-83fe-4b68-814d-933a26d6d567
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GetStatus method [Windows Device Testing Framework], GetStatus method [Windows Device Testing Framework], IWDTFAction2 interface, GetStatus,IWDTFAction2.GetStatus, IWDTFAction2, IWDTFAction2 interface [Windows Device Testing Framework], GetStatus method, IWDTFAction2::GetStatus, Microsoft.WDTF.IWDTFAction2.GetStatus, Microsoft::WDTF::IWDTFAction2::GetStatus, dtf.iwdtfaction2_getstatus, wdtf/IWDTFAction2::GetStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
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
-	IWDTFAction2.GetStatus
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFAction2::GetStatus method
Returns the status code for the last operation.

## Syntax

```
HRESULT GetStatus(
  HRESULT *pResult
);
```

## Parameters

`pResult`

The status code for the last operation.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406311">IWDTFAction2</a>