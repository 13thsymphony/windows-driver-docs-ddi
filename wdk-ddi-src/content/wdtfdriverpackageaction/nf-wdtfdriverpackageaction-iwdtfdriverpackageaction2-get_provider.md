---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.get_Provider
title: IWDTFDriverPackageAction2::get_Provider method
author: windows-driver-content
description: Gets the driver package provider.
old-location: dtf\iwdtfdriverpackageaction2_provider.htm
old-project: dtf
ms.assetid: 1d97bd4b-4e8c-4e36-97cc-c704b85e77ae
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], Provider property, IWDTFDriverPackageAction2.Provider, IWDTFDriverPackageAction2::get_Provider, Microsoft.WDTF.IWDTFDriverPackageAction2.Provider, Microsoft::WDTF::IWDTFDriverPackageAction2::Provider, Provider property [Windows Device Testing Framework], Provider property [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface, dtf.iwdtfdriverpackageaction2_provider, get_Provider,IWDTFDriverPackageAction2.get_Provider, wdtfdriverpackageaction/IWDTFDriverPackageAction2::Provider, wdtfdriverpackageaction/IWDTFDriverPackageAction2::get_Provider
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
-	IWDTFDriverPackageAction2.Provider
-	IWDTFDriverPackageAction2.get_Provider
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# get_Provider method
Gets the driver package provider.

This property is read-only.

## Syntax

````
HRESULT get_Provider(
  [out, retval] BSTR *pVal
);
````

## Parameters

`pVal`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtfdriverpackageaction.h |

## See Also

<a href="..\wdtfdriverpackageaction\nn-wdtfdriverpackageaction-iwdtfdriverpackageaction2.md">IWDTFDriverPackageAction2</a>