---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2.IsRebootRequired
title: IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired method
author: windows-driver-content
description: Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2_isrebootrequired.htm
old-project: dtf
ms.assetid: 598c4e54-74e1-4e95-bdf9-23bc70f4b530
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFEnhancedDeviceTestSupportAction2, IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework], IsRebootRequired method, IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired, IsRebootRequired method [Windows Device Testing Framework], IsRebootRequired method [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportAction2 interface, IsRebootRequired,IWDTFEnhancedDeviceTestSupportAction2.IsRebootRequired, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2.IsRebootRequired, Microsoft::WDTF::IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired, dtf.iwdtfenhanceddevicetestsupportaction2_isrebootrequired, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfedtaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFEDTAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverEDTAction.Interop.dll
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
-	WDTFDriverEDTAction.Interop.dll
api_name:
-	IWDTFEnhancedDeviceTestSupportAction2.IsRebootRequired
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFEnhancedDeviceTestSupportAction2::IsRebootRequired method
Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.

## Syntax

```
HRESULT IsRebootRequired(
  VARIANT_BOOL *pbRebootRequired
);
```

## Parameters

`pbRebootRequired`

True if reboot is required; otherwise, false.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfedtaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450969">IWDTFEnhancedDeviceTestSupportAction2</a>