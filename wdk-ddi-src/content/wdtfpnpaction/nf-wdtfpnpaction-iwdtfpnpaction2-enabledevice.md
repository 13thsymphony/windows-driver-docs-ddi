---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.EnableDevice
title: IWDTFPNPAction2::EnableDevice method
author: windows-driver-content
description: Enables the target device.
old-location: dtf\iwdtfpnpaction2_enabledevice.htm
old-project: dtf
ms.assetid: f11d31ec-71fb-4110-949c-6d33671dc85c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EnableDevice method [Windows Device Testing Framework], EnableDevice method [Windows Device Testing Framework], IWDTFPNPAction2 interface, EnableDevice,IWDTFPNPAction2.EnableDevice, IWDTFPNPAction2, IWDTFPNPAction2 interface [Windows Device Testing Framework], EnableDevice method, IWDTFPNPAction2::EnableDevice, Microsoft.WDTF.IWDTFPNPAction2.EnableDevice, Microsoft::WDTF::IWDTFPNPAction2::EnableDevice, dtf.iwdtfpnpaction2_enabledevice, wdtfpnpaction/IWDTFPNPAction2::EnableDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPNPAction.Interop.dll
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
-	WDTFDriverPNPAction.Interop.dll
api_name:
-	IWDTFPNPAction2.EnableDevice
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# EnableDevice method
Enables the target device.

## Syntax

````
HRESULT EnableDevice(
  [out, retval] VARIANT_BOOL *pbSuccess
);
````

## Parameters

`pbSuccess`

True if the operation succeeds; otherwise, false.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfpnpaction.h |

## See Also

<a href="..\wdtfpnpaction\nn-wdtfpnpaction-iwdtfpnpaction2.md">IWDTFPNPAction2</a>