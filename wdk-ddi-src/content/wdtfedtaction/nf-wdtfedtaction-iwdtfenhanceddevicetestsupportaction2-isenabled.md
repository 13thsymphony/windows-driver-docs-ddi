---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2.IsEnabled
title: IWDTFEnhancedDeviceTestSupportAction2::IsEnabled method
author: windows-driver-content
description: Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2_isenabled.htm
old-project: dtf
ms.assetid: 7d75d8e7-1416-4075-bc75-b4d2cd4f65a5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFEnhancedDeviceTestSupportAction2, IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework], IsEnabled method, IWDTFEnhancedDeviceTestSupportAction2::IsEnabled, IsEnabled method [Windows Device Testing Framework], IsEnabled method [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportAction2 interface, IsEnabled,IWDTFEnhancedDeviceTestSupportAction2.IsEnabled, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2.IsEnabled, Microsoft::WDTF::IWDTFEnhancedDeviceTestSupportAction2::IsEnabled, dtf.iwdtfenhanceddevicetestsupportaction2_isenabled, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::IsEnabled
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
-	IWDTFEnhancedDeviceTestSupportAction2.IsEnabled
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFEnhancedDeviceTestSupportAction2::IsEnabled method
Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled 
on the target device.

## Syntax

```
HRESULT IsEnabled(
  VARIANT_BOOL *pbEnabled
);
```

## Parameters

`pbEnabled`

True if the EDT driver is enabled; otherwise, false.


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