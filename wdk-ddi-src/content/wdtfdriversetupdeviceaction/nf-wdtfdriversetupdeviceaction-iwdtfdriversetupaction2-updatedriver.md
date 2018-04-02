---
UID: NF:wdtfdriversetupdeviceaction.IWDTFDriverSetupAction2.UpdateDriver
title: IWDTFDriverSetupAction2::UpdateDriver method
author: windows-driver-content
description: Updates the target device with a driver from the driver package.
old-location: dtf\iwdtfdriversetupaction2_updatedriver.htm
old-project: dtf
ms.assetid: 4eb49aae-a7de-4038-9d57-003bb30d7ea8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFDriverSetupAction2, IWDTFDriverSetupAction2 interface [Windows Device Testing Framework], UpdateDriver method, IWDTFDriverSetupAction2::UpdateDriver, Microsoft.WDTF.IWDTFDriverSetupAction2.UpdateDriver, Microsoft::WDTF::IWDTFDriverSetupAction2::UpdateDriver, UpdateDriver method [Windows Device Testing Framework], UpdateDriver method [Windows Device Testing Framework], IWDTFDriverSetupAction2 interface, UpdateDriver,IWDTFDriverSetupAction2.UpdateDriver, dtf.iwdtfdriversetupaction2_updatedriver, wdtfdriversetupdeviceaction/IWDTFDriverSetupAction2::UpdateDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfdriversetupdeviceaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverSetupDeviceAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverSetupDeviceAction.Interop.dll
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
-	WDTFDriverSetupDeviceAction.Interop.dll
api_name:
-	IWDTFDriverSetupAction2.UpdateDriver
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFDriverSetupAction2::UpdateDriver method
Updates the target device with a driver from the driver package.

## Syntax

```
HRESULT UpdateDriver(
  IWDTFDriverPackageAction2 *pDp,
  VARIANT_BOOL              *pbReboot
);
```

## Parameters

`pDp`

The driver package.

`pbReboot`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfdriversetupdeviceaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450938">IWDTFDriverSetupAction2</a>