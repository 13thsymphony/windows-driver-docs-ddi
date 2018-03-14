---
UID: NF:wdtf.IWDTFTargets2.Clear
title: IWDTFTargets2::Clear method
author: windows-driver-content
description: Removes all items from the collection.
old-location: dtf\iwdtftargets2_clear.htm
old-project: dtf
ms.assetid: 4fe37240-7cef-4bfb-91be-49a0bca2fa8f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: Clear method [Windows Device Testing Framework], Clear method [Windows Device Testing Framework], IWDTFTargets2 interface, Clear,IWDTFTargets2.Clear, IWDTFTargets2, IWDTFTargets2 interface [Windows Device Testing Framework], Clear method, IWDTFTargets2::Clear, Microsoft.WDTF.IWDTFTargets2.Clear, Microsoft::WDTF::IWDTFTargets2::Clear, dtf.iwdtftargets2_clear, wdtf/IWDTFTargets2::Clear
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
-	IWDTFTargets2.Clear
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# Clear method
Removes all items from the collection.

## Syntax

````
HRESULT Clear();
````

## Parameters

This function has no parameters.

## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

The lifetime of <a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a> interface 
instances are tied to their creator. If you clear all items from a collection, the items are
not destroyed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtftargets2.md">IWDTFTargets2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTargets2::Clear method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>