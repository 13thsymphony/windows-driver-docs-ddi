---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.get_HasCatalog
title: IWDTFDriverPackageAction2::get_HasCatalog method
author: windows-driver-content
description: Gets a value that indicates whether the driver package has a catalog.
old-location: dtf\iwdtfdriverpackageaction2_hascatalog.htm
old-project: dtf
ms.assetid: 0536f452-c513-45dc-9048-5420d2165715
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: HasCatalog property [Windows Device Testing Framework], HasCatalog property [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface, IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], HasCatalog property, IWDTFDriverPackageAction2.HasCatalog, IWDTFDriverPackageAction2::get_HasCatalog, Microsoft.WDTF.IWDTFDriverPackageAction2.HasCatalog, Microsoft::WDTF::IWDTFDriverPackageAction2::HasCatalog, dtf.iwdtfdriverpackageaction2_hascatalog, get_HasCatalog,IWDTFDriverPackageAction2.get_HasCatalog, wdtfdriverpackageaction/IWDTFDriverPackageAction2::HasCatalog, wdtfdriverpackageaction/IWDTFDriverPackageAction2::get_HasCatalog
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
-	IWDTFDriverPackageAction2.HasCatalog
-	IWDTFDriverPackageAction2.get_HasCatalog
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# get_HasCatalog method
Gets a value that indicates whether the driver package has a catalog.

This property is read-only.

## Syntax

````
HRESULT get_HasCatalog(
  [out, retval] VARIANT_BOOL *pbVal
);
````

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

<a href="..\wdtfdriverpackageaction\nn-wdtfdriverpackageaction-iwdtfdriverpackageaction2.md">IWDTFDriverPackageAction2</a>