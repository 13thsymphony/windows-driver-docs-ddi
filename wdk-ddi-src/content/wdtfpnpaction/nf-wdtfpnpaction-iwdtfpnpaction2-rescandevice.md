---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.RescanDevice
title: IWDTFPNPAction2::RescanDevice method
author: windows-driver-content
description: Rescans the target device.
old-location: dtf\iwdtfpnpaction2_rescandevice.htm
old-project: dtf
ms.assetid: 83288eab-020b-4870-9c99-b3215d52658c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFPNPAction2, IWDTFPNPAction2 interface [Windows Device Testing Framework], RescanDevice method, IWDTFPNPAction2::RescanDevice, Microsoft.WDTF.IWDTFPNPAction2.RescanDevice, Microsoft::WDTF::IWDTFPNPAction2::RescanDevice, RescanDevice method [Windows Device Testing Framework], RescanDevice method [Windows Device Testing Framework], IWDTFPNPAction2 interface, RescanDevice,IWDTFPNPAction2.RescanDevice, dtf.iwdtfpnpaction2_rescandevice, wdtfpnpaction/IWDTFPNPAction2::RescanDevice
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
-	IWDTFPNPAction2.RescanDevice
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# RescanDevice method
Rescans the target device.

## Syntax

````
HRESULT RescanDevice(
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