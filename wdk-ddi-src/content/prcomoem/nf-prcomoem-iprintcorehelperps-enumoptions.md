---
UID: NF:prcomoem.IPrintCoreHelperPS.EnumOptions
title: IPrintCoreHelperPS::EnumOptions method
author: windows-driver-content
description: The IPrintCoreHelperPS::EnumOptions method gets a list of available options for the given feature.
old-location: print\iprintcorehelperps_enumoptions.htm
old-project: print
ms.assetid: bd23f4e6-7a99-4347-ae29-a1e832db2e03
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EnumOptions method [Print Devices], EnumOptions method [Print Devices], IPrintCoreHelperPS interface, EnumOptions,IPrintCoreHelperPS.EnumOptions, IPrintCoreHelperPS, IPrintCoreHelperPS interface [Print Devices], EnumOptions method, IPrintCoreHelperPS::EnumOptions, prcomoem/IPrintCoreHelperPS::EnumOptions, print.iprintcorehelperps_enumoptions, print_unidrv-pscript_allplugins_89c5ea61-aedf-43c6-9a8b-020656476f35.xml
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
req.lib: 
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
-	IPrintCoreHelperPS.EnumOptions
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# EnumOptions method
The <b>IPrintCoreHelperPS::EnumOptions</b> method gets a list of available options for the given feature.

## Syntax

````
STDMETHOD EnumOptions(
  [in]  PCSTR pszFeatureKeyword,
  [out] PCSTR *pOptionList[],
  [out] DWORD *pdwNumOptions
);
````

## Parameters

`pszFeatureKeyword`

An ANSI character string that contains the feature whose options are requested.

`pOptionList`



`pdwNumOptions`

A pointer to a variable that receives the number of options in the option array that is pointed to by the <i>pOptionList</i> parameter.


## Return Value

<b>IPrintCoreHelperPS::EnumOptions</b> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## Remarks

When <b>IPrintCoreHelperPS::EnumOptions</b> returns, the option list contains all options, regardless of constraints or other factors.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551977">IPrintCoreHelperPS::EnumFeatures</a>



<a href="..\prcomoem\nn-prcomoem-iprintcorehelperps.md">IPrintCoreHelperPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551972">IPrintCoreHelperPS::EnumConstrainedOptions</a>