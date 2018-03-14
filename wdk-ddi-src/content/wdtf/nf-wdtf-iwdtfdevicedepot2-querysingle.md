---
UID: NF:wdtf.IWDTFDeviceDepot2.QuerySingle
title: IWDTFDeviceDepot2::QuerySingle method
author: windows-driver-content
description: Returns a single target device from the DeviceDepot.
old-location: dtf\iwdtfdevicedepot2_querysingle.htm
old-project: dtf
ms.assetid: 5e471ede-3607-4d4d-a3f0-5396cc62c6c5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFDeviceDepot2, IWDTFDeviceDepot2 interface [Windows Device Testing Framework], QuerySingle method, IWDTFDeviceDepot2::QuerySingle, Microsoft.WDTF.IWDTFDeviceDepot2.QuerySingle, Microsoft::WDTF::IWDTFDeviceDepot2::QuerySingle, QuerySingle method [Windows Device Testing Framework], QuerySingle method [Windows Device Testing Framework], IWDTFDeviceDepot2 interface, QuerySingle,IWDTFDeviceDepot2.QuerySingle, dtf.iwdtfdevicedepot2_querysingle, wdtf/IWDTFDeviceDepot2::QuerySingle
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
-	IWDTFDeviceDepot2.QuerySingle
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# QuerySingle method
Returns a single target device from the DeviceDepot.

## Syntax

````
HRESULT QuerySingle(
  [in]          BSTR         SDEL,
  [out, retval] IWDTFTarget2 **ppTarget
);
````

## Parameters

`SDEL`

The SDEL query string.

`ppTarget`

The requested device.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtfdevicedepot2.md">IWDTFDeviceDepot2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDeviceDepot2::QuerySingle method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>