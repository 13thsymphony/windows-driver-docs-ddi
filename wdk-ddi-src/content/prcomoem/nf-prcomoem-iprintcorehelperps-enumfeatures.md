---
UID: NF:prcomoem.IPrintCoreHelperPS.EnumFeatures
title: IPrintCoreHelperPS::EnumFeatures method
author: windows-driver-content
description: The IPrintCoreHelperPS::EnumFeatures method gets a list of all available features, including synthesized and core driver-implement features.
old-location: print\iprintcorehelperps_enumfeatures.htm
old-project: print
ms.assetid: c67c15a4-3dbf-4317-b6d5-e52f426e7619
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EnumFeatures method [Print Devices], EnumFeatures method [Print Devices], IPrintCoreHelperPS interface, EnumFeatures,IPrintCoreHelperPS.EnumFeatures, IPrintCoreHelperPS, IPrintCoreHelperPS interface [Print Devices], EnumFeatures method, IPrintCoreHelperPS::EnumFeatures, prcomoem/IPrintCoreHelperPS::EnumFeatures, print.iprintcorehelperps_enumfeatures, print_unidrv-pscript_allplugins_06a6f78b-fa5d-496e-b276-f32bba7c2502.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: prcomoem.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Prcomoem.h
api_name:
-	IPrintCoreHelperPS.EnumFeatures
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# EnumFeatures method
The<b> IPrintCoreHelperPS::EnumFeatures</b> method gets a list of all available features, including synthesized and core driver-implement features.

## Syntax

````
STDMETHOD EnumFeatures(
  [out] PCSTR *pFeatureList,
  [out] DWORD *pdwNumFeatures
);
````

## Parameters

`pFeatureList`

A pointer to an array of ANSI character strings that contain all of the features that are available for the current device. The final array element is indicated by a <b>NULL</b> string.

`pdwNumFeatures`

A pointer to a variable that receives the number of feature keywords in the array that is pointed to by the <i>pFeatureList</i> parameter.


## Return Value

<b>IPrintCoreHelperPS::EnumFeatures</b> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |
| **Library** | prcomoem.h |

## See Also

<a href="..\prcomoem\nn-prcomoem-iprintcorehelperps.md">IPrintCoreHelperPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551987">IPrintCoreHelperPS::EnumOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperPS::EnumFeatures method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>