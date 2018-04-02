---
UID: NF:wdtf.IWDTFAction2.EnableObjectLogging
title: IWDTFAction2::EnableObjectLogging method
author: windows-driver-content
description: Enables object logging for the action.
old-location: dtf\iwdtfaction2_enableobjectlogging.htm
old-project: dtf
ms.assetid: d95e49ce-1c6f-4ce5-9f89-68357f700a4b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EnableObjectLogging method [Windows Device Testing Framework], EnableObjectLogging method [Windows Device Testing Framework], IWDTFAction2 interface, EnableObjectLogging,IWDTFAction2.EnableObjectLogging, IWDTFAction2, IWDTFAction2 interface [Windows Device Testing Framework], EnableObjectLogging method, IWDTFAction2::EnableObjectLogging, Microsoft.WDTF.IWDTFAction2.EnableObjectLogging, Microsoft::WDTF::IWDTFAction2::EnableObjectLogging, dtf.iwdtfaction2_enableobjectlogging, wdtf/IWDTFAction2::EnableObjectLogging
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
-	IWDTFAction2.EnableObjectLogging
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFAction2::EnableObjectLogging method
Enables object logging for the action.

## Syntax

```
HRESULT EnableObjectLogging(

);
```

## Parameters

This function has no parameters.

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