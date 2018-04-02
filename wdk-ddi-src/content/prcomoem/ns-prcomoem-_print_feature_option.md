---
UID: NS:prcomoem._PRINT_FEATURE_OPTION
title: "_PRINT_FEATURE_OPTION"
author: windows-driver-content
description: The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature.
old-location: print\print_feature_option.htm
old-project: print
ms.assetid: 82c9c54b-f124-46d7-a3c9-a17fd8028412
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PRINT_FEATURE_OPTION, PRINT_FEATURE_OPTION structure [Print Devices], _PRINT_FEATURE_OPTION, prcomoem/PRINT_FEATURE_OPTION, print.print_feature_option, print_unidrv-pscript_ui_2f776943-da30-40c4-909a-56472768c8df.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	prcomoem.h
api_name:
-	PRINT_FEATURE_OPTION
product: Windows
targetos: Windows
req.typenames: PRINT_FEATURE_OPTION
req.product: Windows 10 or later.
---

# _PRINT_FEATURE_OPTION structure
The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature.

## Syntax
```
typedef struct _PRINT_FEATURE_OPTION {
  PCSTR pszFeature;
  PCSTR pszOption;
} PRINT_FEATURE_OPTION;
```

## Members


`pszFeature`

The printing feature.

`pszOption`

One of the options for the printing feature.

## Remarks
This structure is used by methods that belong to the <b>IPrintCoreHelper</b>, <b>IPrintCoreHelperPS</b>, and <b>IPrintCoreHelperUni</b> interfaces. The methods are listed in the See Also section.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | prcomoem.h (include Prcomoem.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552963">IPrintCoreHelper::SetOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552965">IPrintCoreHelper::WhyConstrained</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552912">IPrintCoreHelperPS::SetOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552915">IPrintCoreHelperPS::WhyConstrained</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552945">IPrintCoreHelperUni::SetOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552947">IPrintCoreHelperUni::WhyConstrained</a>