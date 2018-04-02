---
UID: NF:wdtf.IWDTFStrings2.get__NewEnum
title: IWDTFStrings2::get__NewEnum method
author: windows-driver-content
description: Gets a new iteration variable that the For Each loop structure implicitly uses.
old-location: dtf\iwdtfstrings2__newenum.htm
old-project: dtf
ms.assetid: 1e912b01-e5d1-44f6-b054-1cb5082ccdc4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFStrings2, IWDTFStrings2 interface [Windows Device Testing Framework], _NewEnum property, IWDTFStrings2._NewEnum, IWDTFStrings2::get__NewEnum, Microsoft.WDTF.IWDTFStrings2._NewEnum, Microsoft::WDTF::IWDTFStrings2::_NewEnum, _NewEnum property [Windows Device Testing Framework], _NewEnum property [Windows Device Testing Framework], IWDTFStrings2 interface, dtf.iwdtfstrings2__newenum, get__NewEnum,IWDTFStrings2.get__NewEnum, wdtf/IWDTFStrings2::_NewEnum, wdtf/IWDTFStrings2::get__NewEnum
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
-	IWDTFStrings2._NewEnum
-	IWDTFStrings2.get__NewEnum
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFStrings2::get__NewEnum method
Gets a new iteration variable that the <b>For Each</b> 
loop structure implicitly uses.

This property is read-only.

## Syntax

```
HRESULT get__NewEnum(
  IUnknown **ppNewEnum
);
```

## Parameters

`ppNewEnum`




## Return Value

None

## Remarks

You cannot access the <b>_NewEnum</b> property from the 
JScript programming language.

You must use the Active Template Library (ATL) to implement this functionality. 
For more information about how ATL implements this functionality, see the 
<b>ICollectionOnSTLImpl </b>interface in the MSDN Library.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439274">IWDTFStrings2</a>