---
UID: NF:wdtf.IWDTFStrings2.Remove
title: IWDTFStrings2::Remove method
author: windows-driver-content
description: Removes a string from the collection.
old-location: dtf\iwdtfstrings2_remove.htm
old-project: dtf
ms.assetid: cd32b54a-57e0-496c-b18c-84a6c75d8820
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFStrings2, IWDTFStrings2 interface [Windows Device Testing Framework], Remove method, IWDTFStrings2::Remove, Microsoft.WDTF.IWDTFStrings2.Remove, Microsoft::WDTF::IWDTFStrings2::Remove, Remove method [Windows Device Testing Framework], Remove method [Windows Device Testing Framework], IWDTFStrings2 interface, Remove,IWDTFStrings2.Remove, dtf.iwdtfstrings2_remove, wdtf/IWDTFStrings2::Remove
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
-	IWDTFStrings2.Remove
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFStrings2::Remove method
Removes a string from the collection.

## Syntax

```
HRESULT Remove(
  LONG Index
);
```

## Parameters

`Index`

The 0-based index value of the string to remove.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439274">IWDTFStrings2</a>