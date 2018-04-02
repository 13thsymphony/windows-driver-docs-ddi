---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.get_IsDigitalSigned
title: IWDTFDriverPackageAction2::get_IsDigitalSigned method
author: windows-driver-content
description: Gets a value that indicates whether the driver package is signed.
old-location: dtf\iwdtfdriverpackageaction2_isdigitalsigned.htm
old-project: dtf
ms.assetid: 421682aa-2e21-4650-bae0-f47e6beff632
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], IsDigitalSigned property, IWDTFDriverPackageAction2.IsDigitalSigned, IWDTFDriverPackageAction2::get_IsDigitalSigned, IsDigitalSigned property [Windows Device Testing Framework], IsDigitalSigned property [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface, Microsoft.WDTF.IWDTFDriverPackageAction2.IsDigitalSigned, Microsoft::WDTF::IWDTFDriverPackageAction2::IsDigitalSigned, dtf.iwdtfdriverpackageaction2_isdigitalsigned, get_IsDigitalSigned,IWDTFDriverPackageAction2.get_IsDigitalSigned, wdtfdriverpackageaction/IWDTFDriverPackageAction2::IsDigitalSigned, wdtfdriverpackageaction/IWDTFDriverPackageAction2::get_IsDigitalSigned
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfdriverpackageaction.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverPackageAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPackageAction.Interop.dll
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
-	WDTFDriverPackageAction.Interop.dll
api_name:
-	IWDTFDriverPackageAction2.IsDigitalSigned
-	IWDTFDriverPackageAction2.get_IsDigitalSigned
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFDriverPackageAction2::get_IsDigitalSigned method
Gets a value that indicates whether the driver package is signed.

This property is read-only.

## Syntax

```
HRESULT get_IsDigitalSigned(
  VARIANT_BOOL *pbVal
);
```

## Parameters

`pbVal`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtfdriverpackageaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406427">IWDTFDriverPackageAction2</a>