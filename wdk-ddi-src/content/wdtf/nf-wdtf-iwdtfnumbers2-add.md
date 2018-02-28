---
UID: NF:wdtf.IWDTFNumbers2.Add
title: IWDTFNumbers2::Add method
author: windows-driver-content
description: Adds a single number to the collection.
old-location: dtf\iwdtfnumbers2_add.htm
old-project: dtf
ms.assetid: 162f8fce-c944-4ed2-82f1-332e986b9f77
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: Add method [Windows Device Testing Framework], Add method [Windows Device Testing Framework], IWDTFNumbers2 interface, Add,IWDTFNumbers2.Add, IWDTFNumbers2, IWDTFNumbers2 interface [Windows Device Testing Framework], Add method, IWDTFNumbers2::Add, Microsoft.WDTF.IWDTFNumbers2.Add, Microsoft::WDTF::IWDTFNumbers2::Add, dtf.iwdtfnumbers2_add, wdtf/IWDTFNumbers2::Add
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
-	IWDTFNumbers2.Add
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# Add method
Adds a single number to the collection.

## Syntax

````
HRESULT Add(
  [in] LONG Number
);
````

## Parameters

`Number`

The number to add to this collection.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |
| **Library** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtfnumbers2.md">IWDTFNumbers2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFNumbers2::Add method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>