---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.StopAsync
title: IWDTFSimpleIOStressAction2::StopAsync method
author: windows-driver-content
description: Asynchronously signals the stop event to occur.
old-location: dtf\iwdtfsimpleiostressaction2_stopasync.htm
old-project: dtf
ms.assetid: fac4b59b-da9a-4245-bff0-f9177962c9d6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSimpleIOStressAction2, IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework], StopAsync method, IWDTFSimpleIOStressAction2::StopAsync, Microsoft.WDTF.IWDTFSimpleIOStressAction2.StopAsync, Microsoft::WDTF::IWDTFSimpleIOStressAction2::StopAsync, StopAsync method [Windows Device Testing Framework], StopAsync method [Windows Device Testing Framework], IWDTFSimpleIOStressAction2 interface, StopAsync,IWDTFSimpleIOStressAction2.StopAsync, dtf.iwdtfsimpleiostressaction2_stopasync, wdtfinterfaces/IWDTFSimpleIOStressAction2::StopAsync
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
req.lib: 
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
-	IWDTFSimpleIOStressAction2.StopAsync
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# StopAsync method
Asynchronously signals the stop event to occur.

## Syntax

````
HRESULT StopAsync();
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

## See Also

<a href="..\wdtfinterfaces\nn-wdtfinterfaces-iwdtfsimpleiostressaction2.md">IWDTFSimpleIOStressAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimpleIOStressAction2::StopAsync method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>