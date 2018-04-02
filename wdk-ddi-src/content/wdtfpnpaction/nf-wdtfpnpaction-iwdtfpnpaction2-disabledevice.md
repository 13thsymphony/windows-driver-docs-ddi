---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.DisableDevice
title: IWDTFPNPAction2::DisableDevice method
author: windows-driver-content
description: Disables the target device.
old-location: dtf\iwdtfpnpaction2_disabledevice.htm
old-project: dtf
ms.assetid: b6e3f327-c928-497d-b90c-db6c05b3a7b4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DisableDevice method [Windows Device Testing Framework], DisableDevice method [Windows Device Testing Framework], IWDTFPNPAction2 interface, DisableDevice,IWDTFPNPAction2.DisableDevice, IWDTFPNPAction2, IWDTFPNPAction2 interface [Windows Device Testing Framework], DisableDevice method, IWDTFPNPAction2::DisableDevice, Microsoft.WDTF.IWDTFPNPAction2.DisableDevice, Microsoft::WDTF::IWDTFPNPAction2::DisableDevice, dtf.iwdtfpnpaction2_disabledevice, wdtfpnpaction/IWDTFPNPAction2::DisableDevice
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
-	IWDTFPNPAction2.DisableDevice
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFPNPAction2::DisableDevice method
Disables the target device.

## Syntax

```
HRESULT DisableDevice(
  VARIANT_BOOL *pbSuccess
);
```

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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451065">IWDTFPNPAction2</a>