---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.Stop
title: IWDTFSimpleIOStressAction2::Stop method
author: windows-driver-content
description: Stops the device.
old-location: dtf\iwdtfsimpleiostressaction2_stop.htm
old-project: dtf
ms.assetid: d813b9f4-95f7-49cd-97c0-08a04dbd362e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSimpleIOStressAction2, IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework], Stop method, IWDTFSimpleIOStressAction2::Stop, Microsoft.WDTF.IWDTFSimpleIOStressAction2.Stop, Microsoft::WDTF::IWDTFSimpleIOStressAction2::Stop, Stop method [Windows Device Testing Framework], Stop method [Windows Device Testing Framework], IWDTFSimpleIOStressAction2 interface, Stop,IWDTFSimpleIOStressAction2.Stop, dtf.iwdtfsimpleiostressaction2_stop, wdtfinterfaces/IWDTFSimpleIOStressAction2::Stop
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
-	IWDTFSimpleIOStressAction2.Stop
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# Stop method
Stops the device.

## Syntax

````
HRESULT Stop(
  [out, retval] VARIANT_BOOL *pResult
);
````

## Parameters

`pResult`

True if all of the I/O operations after the last 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973223">Start</a> or 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451185">Continue</a> succeeded; 
otherwise, false.


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimpleIOStressAction2::Stop method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>