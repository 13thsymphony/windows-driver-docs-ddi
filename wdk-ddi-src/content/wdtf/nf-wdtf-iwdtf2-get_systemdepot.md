---
UID: NF:wdtf.IWDTF2.get_SystemDepot
title: IWDTF2::get_SystemDepot method
author: windows-driver-content
description: Gets the SystemDepot object.
old-location: dtf\iwdtf2_systemdepot.htm
old-project: dtf
ms.assetid: 0a377d87-c164-4ac3-9020-7bfe20f78d46
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTF2, IWDTF2 interface [Windows Device Testing Framework], SystemDepot property, IWDTF2.SystemDepot, IWDTF2::get_SystemDepot, Microsoft.WDTF.IWDTF2.SystemDepot, Microsoft::WDTF::IWDTF2::SystemDepot, SystemDepot property [Windows Device Testing Framework], SystemDepot property [Windows Device Testing Framework], IWDTF2 interface, dtf.iwdtf2_systemdepot, get_SystemDepot,IWDTF2.get_SystemDepot, wdtf/IWDTF2::SystemDepot, wdtf/IWDTF2::get_SystemDepot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
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
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTF2.SystemDepot
-	IWDTF2.get_SystemDepot
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# get_SystemDepot method
Gets the SystemDepot object.

This property is read-only.

## Syntax

````
HRESULT get_SystemDepot(
  [out, retval] IWDTFSystemDepot2 **pVal
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
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtf2.md">IWDTF2</a>



<a href="..\wdtf\nn-wdtf-iwdtfsystemdepot2.md">IWDTFSystemDepot2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTF2::SystemDepot property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>