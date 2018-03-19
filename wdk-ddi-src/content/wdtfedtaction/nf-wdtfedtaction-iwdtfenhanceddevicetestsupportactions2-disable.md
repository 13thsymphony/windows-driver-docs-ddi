---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportActions2.Disable
title: IWDTFEnhancedDeviceTestSupportActions2::Disable method
author: windows-driver-content
description: Disables the Enhanced Device Test (EDT) filter driver on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportactions2_disable.htm
old-project: dtf
ms.assetid: aaa9604a-1c82-48c5-ab5d-0251bf9f13cd
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: Disable method [Windows Device Testing Framework], Disable method [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportActions2 interface, Disable,IWDTFEnhancedDeviceTestSupportActions2.Disable, IWDTFEnhancedDeviceTestSupportActions2, IWDTFEnhancedDeviceTestSupportActions2 interface [Windows Device Testing Framework], Disable method, IWDTFEnhancedDeviceTestSupportActions2::Disable, dtf.iwdtfenhanceddevicetestsupportactions2_disable, wdtfedtaction/IWDTFEnhancedDeviceTestSupportActions2::Disable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfedtaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFEDTAction.idl
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
-	wdtfedtaction.h
api_name:
-	IWDTFEnhancedDeviceTestSupportActions2.Disable
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# Disable method
Disables the Enhanced Device Test (EDT) filter driver on the target device.

## Syntax

````
HRESULT Disable(
  [out, retval] VARIANT_BOOL *pbRebootRequired
);
````

## Parameters

`pbRebootRequired`

True if the operation requires a restart to complete; otherwise, false.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdtfedtaction.h |

## See Also

<a href="..\wdtfedtaction\nn-wdtfedtaction-iwdtfenhanceddevicetestsupportactions2.md">IWDTFEnhancedDeviceTestSupportActions2</a>