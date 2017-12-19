---
UID: NF.prcomoem.IPrintCoreHelperPS.EnumFeatures
title: IPrintCoreHelperPS::EnumFeatures method
author: windows-driver-content
description: The IPrintCoreHelperPS::EnumFeatures method gets a list of all available features, including synthesized and core driver-implement features.
old-location: print\iprintcorehelperps_enumfeatures.htm
old-project: print
ms.assetid: c67c15a4-3dbf-4317-b6d5-e52f426e7619
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintCoreHelperPS, IPrintCoreHelperPS::EnumFeatures, EnumFeatures
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
req.alt-api: IPrintCoreHelperPS.EnumFeatures
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

# IPrintCoreHelperPS::EnumFeatures method



## -description
The<b> IPrintCoreHelperPS::EnumFeatures</b> method gets a list of all available features, including synthesized and core driver-implement features.



## -syntax

````
STDMETHOD EnumFeatures(
  [out] PCSTR *pFeatureList,
  [out] DWORD *pdwNumFeatures
);
````


## -parameters

### -param pFeatureList [out]

A pointer to an array of ANSI character strings that contain all of the features that are available for the current device. The final array element is indicated by a <b>NULL</b> string.


### -param pdwNumFeatures [out]

A pointer to a variable that receives the number of feature keywords in the array that is pointed to by the <i>pFeatureList</i> parameter.


## -returns
<b>IPrintCoreHelperPS::EnumFeatures</b> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.


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
<a href="print.iprintcorehelperps_enumoptions">IPrintCoreHelperPS::EnumOptions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperPS::EnumFeatures method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

