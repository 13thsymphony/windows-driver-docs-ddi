---
UID: NF:wdtf.IWDTFTarget2.GetValueStrings
title: IWDTFTarget2::GetValueStrings method
author: windows-driver-content
description: Returns a collection of string values from the target that are associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluestrings.htm
old-project: dtf
ms.assetid: 2bc18baa-77e0-4ce1-85d9-55817333ecaa
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetValueStrings method [Windows Device Testing Framework], GetValueStrings method [Windows Device Testing Framework], IWDTFTarget2 interface, GetValueStrings,IWDTFTarget2.GetValueStrings, IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], GetValueStrings method, IWDTFTarget2::GetValueStrings, Microsoft.WDTF.IWDTFTarget2.GetValueStrings, Microsoft::WDTF::IWDTFTarget2::GetValueStrings, dtf.iwdtftarget2_getvaluestrings, wdtf/IWDTFTarget2::GetValueStrings
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
-	IWDTFTarget2.GetValueStrings
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# GetValueStrings method
Returns a collection of string values from the target that are associated 
with a specified attribute.

## Syntax

````
HRESULT GetValueStrings(
  [in]          BSTR          SDEL,
  [out, retval] IWDTFStrings2 **ppValues
);
````

## Parameters

`SDEL`

An SDEL statement that specifies the attribute value to retrieve.

`ppValues`

The address of a variable that receives the result of this method.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

You specify the field that the<b> GetValueStrings</b> method retrieves 
by using a regular <a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValueStrings</b> 
to work properly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>