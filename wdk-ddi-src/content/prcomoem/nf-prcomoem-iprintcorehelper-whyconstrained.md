---
UID: NF:prcomoem.IPrintCoreHelper.WhyConstrained
title: IPrintCoreHelper::WhyConstrained method
author: windows-driver-content
description: The IPrintCoreHelper::WhyConstrained method provides a list of options that are constraining the specified feature-option pair in the current configuration.
old-location: print\iprintcorehelper_whyconstrained.htm
old-project: print
ms.assetid: de3fdbd4-9647-4369-9c23-4779aa768b1b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintCoreHelper, IPrintCoreHelper interface [Print Devices], WhyConstrained method, IPrintCoreHelper::WhyConstrained, WhyConstrained method [Print Devices], WhyConstrained method [Print Devices], IPrintCoreHelper interface, WhyConstrained,IPrintCoreHelper.WhyConstrained, prcomoem/IPrintCoreHelper::WhyConstrained, print.iprintcorehelper_whyconstrained, print_unidrv-pscript_allplugins_256e3fde-bcef-4883-99bc-803a3de99841.xml
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
-	prcomoem.h
api_name:
-	IPrintCoreHelper.WhyConstrained
product:
- Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# IPrintCoreHelper::WhyConstrained method
The <b>IPrintCoreHelper::WhyConstrained</b> method provides a list of options that are constraining the specified feature-option pair in the current configuration.

## Syntax

```
HRESULT WhyConstrained(
  CONST DEVMODE              *pDevmode,
  OPTIONAL DWORD             cbSize,
  PCSTR                      pszFeatureKeyword,
  PCSTR                      pszOptionKeyword,
  CONST PRINT_FEATURE_OPTION **ppFOConstraints,
  DWORD                      *pdwNumOptions
);
```

## Parameters

`pDevmode`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. If this pointer is provided, <b>IPrintCoreHelper::WhyConstrained</b> should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from either <a href="https://msdn.microsoft.com/library/windows/hardware/ff553205">IPrintOemPS::DevMode</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff554230">IPrintOemUni::DevMode</a>, this parameter is required. In most other situations, the parameter should be <b>NULL</b>. When the core driver sets <i>pDevmode</i> to <b>NULL</b>, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a>, is being serviced by the core driver's UI module.

`cbSize`

The size, in bytes, of the DEVMODEW structure that is pointed to by the <i>pDevmode</i> parameter.

`pszFeatureKeyword`

A pointer to an ANSI string that contains the name of the feature. The feature name should correspond to the keyword that is used in the GPD or PPD file.

`pszOptionKeyword`

A pointer to an ANSI string that contains the name of the option. The option name should correspond to the keyword that is used in the GPD or PPD file.

`ppFOConstraints`

A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561057">PRINT_FEATURE_OPTION</a> elements. When <b>IPrintCoreHelper::WhyConstrained</b> returns, the array contains a list of feature-element pairs of the options that constrain the options that are specified in the <i>pszOptionKeyword </i>parameter.

`pdwNumOptions`

A pointer to a variable that receives the number of feature-option pairs in the array that is pointed to by the <i>ppFOConstraints</i> parameter.


## Return Value

<b>IPrintCoreHelper::WhyConstrained</b> should return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
One or more of the arguments is invalid, or the feature was not supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
Memory for the result array could not be allocated.

</td>
</tr>
</table>

## Remarks

If the specified feature-option pair is not constrained, <b>IPrintCoreHelper::WhyConstrained</b> will return S_OK but will return with *<i>pdwFOPairs</i> set to 0 and with *<i>ppFOConstraints</i>[0] set to <b>NULL</b>.

Note that the results from this method might not contain all of the options that affect the currently selected option. For Unidrv drivers, this list will include at least one option from each set of constraints that is active. If there are invalid combinations that list more than two feature-option pairs, however, only one option from the combination will be included in the list.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |

## See Also

<a href="https://msdn.microsoft.com/db13410f-e4cb-4077-bb4b-7963e97b435c">IPrintCoreHelper</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552952">IPrintCoreHelper::EnumConstrainedOptions</a>