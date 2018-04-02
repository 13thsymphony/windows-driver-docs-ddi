---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.RemoveDevice
title: IWDTFPNPActions2::RemoveDevice method
author: windows-driver-content
description: Removes the device.
old-location: dtf\iwdtfpnpactions2_removedevice.htm
old-project: dtf
ms.assetid: 8926e96e-b738-47ff-a5c4-8bc15943c6a4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFPNPActions2, IWDTFPNPActions2 interface [Windows Device Testing Framework], RemoveDevice method, IWDTFPNPActions2::RemoveDevice, RemoveDevice method [Windows Device Testing Framework], RemoveDevice method [Windows Device Testing Framework], IWDTFPNPActions2 interface, RemoveDevice,IWDTFPNPActions2.RemoveDevice, dtf.iwdtfpnpactions2_removedevice, wdtfpnpaction/IWDTFPNPActions2::RemoveDevice
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
-	IWDTFPNPActions2.RemoveDevice
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFPNPActions2::RemoveDevice method
Removes the device.

## Syntax

```
HRESULT RemoveDevice(
  VARIANT_BOOL *pbSuccess
);
```

## Parameters

`pbSuccess`

True if the operation succeeds; otherwise, false.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

Under the covers, this will call DIF_REMOVE.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdtfpnpaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451094">IWDTFPNPActions2</a>