---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.GetQueryForDeviceUsingPackage
title: IWDTFDriverPackageAction2::GetQueryForDeviceUsingPackage method
author: windows-driver-content
description: Returns an SDEL statement that queries for all devices that use the driver package.
old-location: dtf\iwdtfdriverpackageaction2_getqueryfordeviceusingpackage.htm
old-project: dtf
ms.assetid: c7d73c86-0ac4-4e87-8f82-39be2329dafd
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GetQueryForDeviceUsingPackage,IWDTFDriverPackageAction2.GetQueryForDeviceUsingPackage, GetQueryForDevicesUsingPackage method [Windows Device Testing Framework], GetQueryForDevicesUsingPackage method [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface, IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], GetQueryForDevicesUsingPackage method, IWDTFDriverPackageAction2::GetQueryForDeviceUsingPackage, IWDTFDriverPackageAction2::GetQueryForDevicesUsingPackage, Microsoft.WDTF.IWDTFDriverPackageAction2.GetQueryForDevicesUsingPackage, Microsoft::WDTF::IWDTFDriverPackageAction2::GetQueryForDevicesUsingPackage, dtf.iwdtfdriverpackageaction2_getqueryfordeviceusingpackage, wdtfdriverpackageaction/IWDTFDriverPackageAction2::GetQueryForDevicesUsingPackage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfdriverpackageaction.h
req.include-header: 
req.target-type: Desktop
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
-	IWDTFDriverPackageAction2.GetQueryForDevicesUsingPackage
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFDriverPackageAction2::GetQueryForDeviceUsingPackage method
Returns an SDEL statement that queries for all devices that use the driver package.

## Syntax

```
HRESULT GetQueryForDeviceUsingPackage(
  BSTR *pSDEL
);
```

## Parameters

`pSDEL`

&gt;The SDEL statement.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfdriverpackageaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406427">IWDTFDriverPackageAction2</a>