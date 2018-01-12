---
UID: NF:prcomoem.IPrintCoreHelperUni.EnumOptions
title: IPrintCoreHelperUni::EnumOptions method
author: windows-driver-content
description: The IPrintCoreHelperUni::EnumOptions method gets a list of available options for the given feature.
old-location: print\iprintcorehelperuni_enumoptions.htm
old-project: print
ms.assetid: 07ed6417-1cdc-4a56-88c3-c2171c54e77c
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintCoreHelperUni, IPrintCoreHelperUni::EnumOptions, EnumOptions
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
req.alt-api: IPrintCoreHelperUni.EnumOptions
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelperUni::EnumOptions method



## -description
The <code>IPrintCoreHelperUni::EnumOptions</code> method gets a list of available options for the given feature. 



## -syntax

````
STDMETHOD EnumOptions(
  [in]  PCSTR pszFeatureKeyword,
  [out] PCSTR *pOptionList[],
  [out] DWORD *pdwNumOptions
);
````


## -parameters

### -param pszFeatureKeyword [in]

An ANSI character string that contains the feature whose options are requested. 


### -param pOptionList[] [out]

A pointer to an array of ANSI character strings that contain all of the options for the feature specified in the <i>pszFeatureKeyword</i> parameter. <code>IPrintCoreHelperUni::EnumOptions</code> is responsible for allocating the memory for the array. The last element of the array must be a <b>NULL</b> string.


### -param pdwNumOptions [out]

A pointer to a variable that receives the number of options in the option array that is pointed to by the <i>pOptionList</i> parameter.


## -returns
<code>IPrintCoreHelperUni::EnumOptions</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.


## -remarks
When <code>IPrintCoreHelperUni::EnumOptions</code> returns, the option list contains all options, regardless of constraints or other factors.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552929">IPrintCoreHelperUni::EnumConstrainedOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552931">IPrintCoreHelperUni::EnumFeatures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperUni::EnumOptions method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

