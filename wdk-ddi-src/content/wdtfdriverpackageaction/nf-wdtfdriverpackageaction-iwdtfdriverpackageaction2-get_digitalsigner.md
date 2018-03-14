---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.get_DigitalSigner
title: IWDTFDriverPackageAction2::get_DigitalSigner method
author: windows-driver-content
description: Gets the digital signer.
old-location: dtf\iwdtfdriverpackageaction2_digitalsigner.htm
old-project: dtf
ms.assetid: ab544760-7539-4e16-b1c3-457629ce78aa
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DigitalSigner property [Windows Device Testing Framework], DigitalSigner property [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface, IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], DigitalSigner property, IWDTFDriverPackageAction2.DigitalSigner, IWDTFDriverPackageAction2::get_DigitalSigner, Microsoft.WDTF.IWDTFDriverPackageAction2.DigitalSigner, Microsoft::WDTF::IWDTFDriverPackageAction2::DigitalSigner, dtf.iwdtfdriverpackageaction2_digitalsigner, get_DigitalSigner,IWDTFDriverPackageAction2.get_DigitalSigner, wdtfdriverpackageaction/IWDTFDriverPackageAction2::DigitalSigner, wdtfdriverpackageaction/IWDTFDriverPackageAction2::get_DigitalSigner
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
-	IWDTFDriverPackageAction2.DigitalSigner
-	IWDTFDriverPackageAction2.get_DigitalSigner
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# get_DigitalSigner method
Gets the digital signer.

This property is read-only.

## Syntax

````
HRESULT get_DigitalSigner(
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDriverPackageAction2::DigitalSigner property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>