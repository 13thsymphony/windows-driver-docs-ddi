---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.get_InfFileName
title: IWDTFDriverPackageAction2::get_InfFileName method
author: windows-driver-content
description: Gets the INF file name.
old-location: dtf\iwdtfdriverpackageaction2_inffilename.htm
old-project: dtf
ms.assetid: 9c2dae4e-05e8-4063-993f-f505d25004df
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], InfFileName property, IWDTFDriverPackageAction2.InfFileName, IWDTFDriverPackageAction2::get_InfFileName, InfFileName property [Windows Device Testing Framework], InfFileName property [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface, Microsoft.WDTF.IWDTFDriverPackageAction2.InfFileName, Microsoft::WDTF::IWDTFDriverPackageAction2::InfFileName, dtf.iwdtfdriverpackageaction2_inffilename, get_InfFileName,IWDTFDriverPackageAction2.get_InfFileName, wdtfdriverpackageaction/IWDTFDriverPackageAction2::InfFileName, wdtfdriverpackageaction/IWDTFDriverPackageAction2::get_InfFileName
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
-	IWDTFDriverPackageAction2.InfFileName
-	IWDTFDriverPackageAction2.get_InfFileName
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# get_InfFileName method
Gets the INF file name.

This property is read-only.

## Syntax

````
HRESULT get_InfFileName(
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDriverPackageAction2::InfFileName property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>