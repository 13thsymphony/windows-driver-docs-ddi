---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.get_IsImported
title: IWDTFDriverPackageAction2::get_IsImported method
author: windows-driver-content
description: Gets a value that indicates whether the driver package is imported.
old-location: dtf\iwdtfdriverpackageaction2_isimported.htm
old-project: dtf
ms.assetid: 9385ad16-843a-4454-ab58-5ccecc3cf6e8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], IsImported property, IWDTFDriverPackageAction2.IsImported, IWDTFDriverPackageAction2::get_IsImported, IsImported property [Windows Device Testing Framework], IsImported property [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface, Microsoft.WDTF.IWDTFDriverPackageAction2.IsImported, Microsoft::WDTF::IWDTFDriverPackageAction2::IsImported, dtf.iwdtfdriverpackageaction2_isimported, get_IsImported,IWDTFDriverPackageAction2.get_IsImported, wdtfdriverpackageaction/IWDTFDriverPackageAction2::IsImported, wdtfdriverpackageaction/IWDTFDriverPackageAction2::get_IsImported
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
-	IWDTFDriverPackageAction2.IsImported
-	IWDTFDriverPackageAction2.get_IsImported
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# get_IsImported method
Gets a value that indicates whether the driver package is imported.

This property is read-only.

## Syntax

````
HRESULT get_IsImported(
  [out, retval] VARIANT_BOOL *pbImported
);
````

## Parameters

`pbImported`




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