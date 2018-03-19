---
UID: NF:wdtf.IWDTFStrings2.Add
title: IWDTFStrings2::Add method
author: windows-driver-content
description: Adds a single string to the collection.
old-location: dtf\iwdtfstrings2_add.htm
old-project: dtf
ms.assetid: 44a62325-4135-483d-adb4-e73803190541
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: Add method [Windows Device Testing Framework], Add method [Windows Device Testing Framework], IWDTFStrings2 interface, Add,IWDTFStrings2.Add, IWDTFStrings2, IWDTFStrings2 interface [Windows Device Testing Framework], Add method, IWDTFStrings2::Add, Microsoft.WDTF.IWDTFStrings2.Add, Microsoft::WDTF::IWDTFStrings2::Add, dtf.iwdtfstrings2_add, wdtf/IWDTFStrings2::Add
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
-	IWDTFStrings2.Add
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# Add method
Adds a single string to the collection.

## Syntax

````
HRESULT Add(
  [in] BSTR pString
);
````

## Parameters

`pString`

The string to add to this collection.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtfstrings2.md">IWDTFStrings2</a>