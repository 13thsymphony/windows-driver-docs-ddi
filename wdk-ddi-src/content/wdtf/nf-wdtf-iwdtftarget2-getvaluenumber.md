---
UID: NF:wdtf.IWDTFTarget2.GetValueNumber
title: IWDTFTarget2::GetValueNumber method
author: windows-driver-content
description: Returns a number value from the target that is associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluenumber.htm
old-project: dtf
ms.assetid: 16f0e9be-129a-4d7d-94c8-bd27ec010b26
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetValueNumber method [Windows Device Testing Framework], GetValueNumber method [Windows Device Testing Framework], IWDTFTarget2 interface, GetValueNumber,IWDTFTarget2.GetValueNumber, IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], GetValueNumber method, IWDTFTarget2::GetValueNumber, Microsoft.WDTF.IWDTFTarget2.GetValueNumber, Microsoft::WDTF::IWDTFTarget2::GetValueNumber, dtf.iwdtftarget2_getvaluenumber, wdtf/IWDTFTarget2::GetValueNumber
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
req.lib: wdtf.h
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
-	IWDTFTarget2.GetValueNumber
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# GetValueNumber method
Returns a number value from the target that is associated with a specified attribute.

## Syntax

````
HRESULT GetValueNumber(
  [in]          BSTR SDEL,
  [out, retval] LONG *pValue
);
````

## Parameters

`SDEL`

An SDEL statement that specifies the attribute value to retrieve.

`pValue`

The address of a variable that receives the result of this method.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

You specify the field that the<b> GetValueNumber</b> method retrieves 
by using a regular <a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValueNumber</b> 
to work properly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |
| **Library** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTarget2::GetValueNumber method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>