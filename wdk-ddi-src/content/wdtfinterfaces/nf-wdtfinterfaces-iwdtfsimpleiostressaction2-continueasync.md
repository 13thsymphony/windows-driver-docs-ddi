---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.ContinueAsync
title: IWDTFSimpleIOStressAction2::ContinueAsync method
author: windows-driver-content
description: Asynchronously signals the I/O to continue.
old-location: dtf\iwdtfsimpleiostressaction2_continueasync.htm
old-project: dtf
ms.assetid: 5297881a-34ba-4fa7-a116-a890ce8b7434
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ContinueAsync method [Windows Device Testing Framework], ContinueAsync method [Windows Device Testing Framework], IWDTFSimpleIOStressAction2 interface, ContinueAsync,IWDTFSimpleIOStressAction2.ContinueAsync, IWDTFSimpleIOStressAction2, IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework], ContinueAsync method, IWDTFSimpleIOStressAction2::ContinueAsync, Microsoft.WDTF.IWDTFSimpleIOStressAction2.ContinueAsync, Microsoft::WDTF::IWDTFSimpleIOStressAction2::ContinueAsync, dtf.iwdtfsimpleiostressaction2_continueasync, wdtfinterfaces/IWDTFSimpleIOStressAction2::ContinueAsync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfinterfaces.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFInterfaces.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFInterfaces.Interop.dll
req.type-library: 
req.lib: wdtfinterfaces.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFInterfaces.Interop.dll
api_name:
-	IWDTFSimpleIOStressAction2.ContinueAsync
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# ContinueAsync method
Asynchronously signals the I/O to continue.

## Syntax

````
HRESULT ContinueAsync();
````

## Parameters

This function has no parameters.

## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfinterfaces.h |
| **Library** | wdtfinterfaces.h |

## See Also

<a href="..\wdtfinterfaces\nn-wdtfinterfaces-iwdtfsimpleiostressaction2.md">IWDTFSimpleIOStressAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimpleIOStressAction2::ContinueAsync method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>