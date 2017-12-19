---
UID: NF.prcomoem.IPrintCoreHelperUni.EnumConstrainedOptions
title: IPrintCoreHelperUni::EnumConstrainedOptions method
author: windows-driver-content
description: The IPrintCoreHelperUni::EnumConstrainedOptions method provides a list of all of the options that are constrained in a particular feature, based on current settings.
old-location: print\iprintcorehelperuni_enumconstrainedoptions.htm
old-project: print
ms.assetid: 362d858a-5087-4cd2-8778-e6564297bc8f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintCoreHelperUni, IPrintCoreHelperUni::EnumConstrainedOptions, EnumConstrainedOptions
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
req.alt-api: IPrintCoreHelperUni.EnumConstrainedOptions
req.alt-loc: Prcomoem.h
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
req.product: Windows 10 or later.
---

# IPrintCoreHelperUni::EnumConstrainedOptions method



## -description
The <code>IPrintCoreHelperUni::EnumConstrainedOptions</code> method provides a list of all of the options that are constrained in a particular feature, based on current settings.



## -syntax

````
STDMETHOD EnumConstrainedOptions(
  [in, optional] CONST DEVMODE *pDevmode,
  [in]           DWORD         cbSize,
  [in]           PCSTR         pszFeatureKeyword,
  [out]          PCSTR         *pConstrainedOptionList[],
  [out]          DWORD         *pdwNumOptions
);
````


## -parameters

### -param pDevmode [in, optional]

A pointer to a <a href="display.devmodew">DEVMODEW</a> structure. If this pointer is provided, <code>IPrintCoreHelperUni::EnumConstrainedOptions</code> should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from <a href="print.iprintoemuni_devmode">IPrintOemUni::DevMode</a>, this parameter is required. In most other situations, the parameter should be <b>NULL</b>. When the core driver sets <i>pDevmode</i> to <b>NULL</b>, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as <a href="print.drvdocumentpropertysheets">DrvDocumentPropertySheets</a>, is being serviced by the core driver's UI module.


### -param cbSize [in]

The size, in bytes, of the DEVMODEW structure that is pointed to by the <i>pDevmode</i> parameter.


### -param pszFeatureKeyword [in]

A string of ANSI characters that contains the feature name.


### -param pConstrainedOptionList[] [out]

A pointer to an array of ANSI character strings. When <code>IPrintCoreHelperUni::EnumConstrainedOptions</code> returns, these strings will contain the names of all of the options that are constrained within the specified feature. The caller is not responsible for freeing the array or the individual strings in the array.


### -param pdwNumOptions [out]

A pointer to a variable that receives the number of constrained options in the array that is pointed to by the <i>pConstrainedOptionList</i> parameter.


## -returns
<code>IPrintCoreHelperUni::EnumConstrainedOptions</code> should return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The constrained options were set for the specified feature.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The caller provided information that resulted in an invalid request, such as a request for a feature that does not exist.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>One or more of the arguments were invalid. This value might mean that the feature is not supported.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>There was not enough memory to create the options array or the core driver could not service the request due to lack of memory.
<dl>
<dt><b>E_UNEXPECTED, or other failures not listed here</b></dt>
</dl>An unexpected condition occurred. The core driver is probably in an invalid state. The caller should exit with a failure code.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.iprintcorehelperuni_enumoptions">IPrintCoreHelperUni::EnumOptions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperUni::EnumConstrainedOptions method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

