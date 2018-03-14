---
UID: NF:wdtf.IWDTFTarget2.GetValueLongNumbers
title: IWDTFTarget2::GetValueLongNumbers method
author: windows-driver-content
description: Returns a collection of long number values from the target that are associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluelongnumbers.htm
old-project: dtf
ms.assetid: 178a28be-b592-45a7-8d46-47cbf9904fc6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetValueLongNumbers method [Windows Device Testing Framework], GetValueLongNumbers method [Windows Device Testing Framework], IWDTFTarget2 interface, GetValueLongNumbers,IWDTFTarget2.GetValueLongNumbers, IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], GetValueLongNumbers method, IWDTFTarget2::GetValueLongNumbers, Microsoft.WDTF.IWDTFTarget2.GetValueLongNumbers, Microsoft::WDTF::IWDTFTarget2::GetValueLongNumbers, dtf.iwdtftarget2_getvaluelongnumbers, wdtf/IWDTFTarget2::GetValueLongNumbers
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
-	IWDTFTarget2.GetValueLongNumbers
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# GetValueLongNumbers method
Returns a collection of long number values from the target that are associated with a specified attribute.

## Syntax

````
HRESULT GetValueLongNumbers(
  [in]          BSTR              SDEL,
  [out, retval] IWDTFLongNumbers2 **ppValue
);
````

## Parameters

`SDEL`

An SDEL statement that specifies the attribute value to retrieve.

`ppValue`

The address of a variable that receives the result of this method.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

You specify the field that the<b> GetValueLongNumbers</b> method retrieves 
by using a regular <a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValueLongNumbers</b> 
to work properly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTarget2::GetValueLongNumbers method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>