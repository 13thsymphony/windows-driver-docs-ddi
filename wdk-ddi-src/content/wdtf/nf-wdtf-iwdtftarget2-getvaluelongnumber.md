---
UID: NF:wdtf.IWDTFTarget2.GetValueLongNumber
title: IWDTFTarget2::GetValueLongNumber method
author: windows-driver-content
description: Returns a long number value from the target that is associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluelongnumber.htm
old-project: dtf
ms.assetid: 9336d850-1d42-47e5-9a69-f15e1147a71f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GetValueLongNumber method [Windows Device Testing Framework], GetValueLongNumber method [Windows Device Testing Framework], IWDTFTarget2 interface, GetValueLongNumber,IWDTFTarget2.GetValueLongNumber, IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], GetValueLongNumber method, IWDTFTarget2::GetValueLongNumber, Microsoft.WDTF.IWDTFTarget2.GetValueLongNumber, Microsoft::WDTF::IWDTFTarget2::GetValueLongNumber, dtf.iwdtftarget2_getvaluelongnumber, wdtf/IWDTFTarget2::GetValueLongNumber
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
-	IWDTFTarget2.GetValueLongNumber
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFTarget2::GetValueLongNumber method
Returns a long number value from the target that is associated with a specified attribute.

## Syntax

```
HRESULT GetValueLongNumber(
  BSTR     SDEL,
  LONGLONG *pValue
);
```

## Parameters

`SDEL`

An SDEL statement that specifies the attribute value to retrieve.

`pValue`

The address of a variable that receives the result of this method.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

You specify the field that the<b> GetValueLongNumber</b> method retrieves 
by using a regular <a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValueLongNumber</b> 
to work properly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a>