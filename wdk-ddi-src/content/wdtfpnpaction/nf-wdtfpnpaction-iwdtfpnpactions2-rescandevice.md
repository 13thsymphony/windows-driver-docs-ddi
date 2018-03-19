---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.RescanDevice
title: IWDTFPNPActions2::RescanDevice method
author: windows-driver-content
description: Rescans the target device.
old-location: dtf\iwdtfpnpactions2_rescandevice.htm
old-project: dtf
ms.assetid: c5b2df39-e631-448e-a2fb-6424f86fc19e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFPNPActions2, IWDTFPNPActions2 interface [Windows Device Testing Framework], RescanDevice method, IWDTFPNPActions2::RescanDevice, RescanDevice method [Windows Device Testing Framework], RescanDevice method [Windows Device Testing Framework], IWDTFPNPActions2 interface, RescanDevice,IWDTFPNPActions2.RescanDevice, dtf.iwdtfpnpactions2_rescandevice, wdtfpnpaction/IWDTFPNPActions2::RescanDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
req.max-support: 
req.namespace: 
req.assembly: 
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
-	wdtfpnpaction.h
api_name:
-	IWDTFPNPActions2.RescanDevice
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
| **Target Platform** | Desktop |
| **Header** | wdtfpnpaction.h |

## See Also

<a href="..\wdtfpnpaction\nn-wdtfpnpaction-iwdtfpnpactions2.md">IWDTFPNPActions2</a>