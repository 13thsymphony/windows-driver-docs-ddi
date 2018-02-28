---
UID: NF:prcomoem.IPrintCoreHelperUni.WhyConstrained
title: IPrintCoreHelperUni::WhyConstrained method
author: windows-driver-content
description: The IPrintCoreHelperUni::WhyConstrained method provides a list of options that constrain the specified feature-option pair in the current configuration.
old-location: print\iprintcorehelperuni_whyconstrained.htm
old-project: print
ms.assetid: 99cd35f3-ebae-4ef2-b6fa-96853b3639ee
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintCoreHelperUni, IPrintCoreHelperUni interface [Print Devices], WhyConstrained method, IPrintCoreHelperUni::WhyConstrained, WhyConstrained method [Print Devices], WhyConstrained method [Print Devices], IPrintCoreHelperUni interface, WhyConstrained,IPrintCoreHelperUni.WhyConstrained, prcomoem/IPrintCoreHelperUni::WhyConstrained, print.iprintcorehelperuni_whyconstrained, print_unidrv-pscript_allplugins_82445c6f-68d1-41df-b94f-243cd072e1a0.xml
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
-	IPrintCoreHelperUni.WhyConstrained
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# WhyConstrained method
The <code>IPrintCoreHelperUni::WhyConstrained</code> method provides a list of options that constrain the specified feature-option pair in the current configuration.

## Syntax

````
STDMETHOD WhyConstrained(
  [in, optional] CONST DEVMODE              *pDevmode,
  [in]           DWORD                      cbSize,
  [in]           PCSTR                      pszFeatureKeyword,
  [in]           PCSTR                      pszOptionKeyword,
  [out]          CONST PRINT_FEATURE_OPTION **ppFOConstraints,
  [out]          DWORD                      *pdwNumOptions
);
````

## Parameters

`pDevmode`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. If this pointer is provided, <code>IPrintCoreHelperUni::WhyConstrained</code> should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from <a href="https://msdn.microsoft.com/library/windows/hardware/ff554230">IPrintOemUni::DevMode</a>, this parameter is required. In most other situations, the parameter should be <b>NULL</b>. When the core driver sets <i>pDevmode</i> to <b>NULL</b>, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a>, is being serviced by the core driver's UI module.

`cbSize`

The size, in bytes, of the DEVMODEW structure that is pointed to by the <i>pDevmode</i> parameter.

`pszFeatureKeyword`

A pointer to an ANSI string that contains the name of the feature. The feature name should correspond to the keyword that is used in the GPD file.

`pszOptionKeyword`

A pointer to an ANSI string that contains the name of the option. The option name should correspond to the keyword that is used in the GPD file.

`ppFOConstraints`

A pointer to an array of <a href="..\prcomoem\ns-prcomoem-_print_feature_option.md">PRINT_FEATURE_OPTION</a> elements. When <code>IPrintCoreHelperUni::WhyConstrained</code> returns, the array contains a list of feature-element pairs of the options that constrain the options that are specified in the <i>pszOptionKeyword</i> parameter.

`pdwNumOptions`

A pointer to a variable that receives the number of feature-option pairs in the array pointed to by the <i>ppFOConstraints</i> parameter.


## Return Value

<code>IPrintCoreHelperUni::WhyConstrained</code> should return one of the following values.

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
 

For other failures, the method should return a standard COM error code.

## Remarks

If the specified feature-option pair is not constrained, <code>IPrintCoreHelperUni::WhyConstrained</code> will return S_OK but will return with *<i>pdwFOPairs</i> set to 0 and with *<i>ppFOConstraints</i>[0] set to <b>NULL</b>.

Note that the results from this method might not contain all of the options that affect the currently selected option. If there are invalid combinations that list more than two feature-option pairs, however, only one option from the combination will be included in the list.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |
| **Library** | prcomoem.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552929">IPrintCoreHelperUni::EnumConstrainedOptions</a>



<a href="..\prcomoem\nn-prcomoem-iprintcorehelperuni.md">IPrintCoreHelperUni</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperUni::WhyConstrained method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>