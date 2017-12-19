---
UID: NS.PRCOMOEM._PRINT_FEATURE_OPTION
title: _PRINT_FEATURE_OPTION
author: windows-driver-content
description: The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature.
old-location: print\print_feature_option.htm
old-project: print
ms.assetid: 82c9c54b-f124-46d7-a3c9-a17fd8028412
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _PRINT_FEATURE_OPTION, PRINT_FEATURE_OPTION
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
req.alt-api: PRINT_FEATURE_OPTION
req.alt-loc: prcomoem.h
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

# _PRINT_FEATURE_OPTION structure



## -description
The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature.



## -syntax

````
typedef struct _PRINT_FEATURE_OPTION {
  PCSTR pszFeature;
  PCSTR pszOption;
} PRINT_FEATURE_OPTION;
````


## -struct-fields

### -field pszFeature

The printing feature.


### -field pszOption

One of the options for the printing feature.


## -remarks
This structure is used by methods that belong to the <b>IPrintCoreHelper</b>, <b>IPrintCoreHelperPS</b>, and <b>IPrintCoreHelperUni</b> interfaces. The methods are listed in the See Also section.


## -requirements
<table>
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
<a href="print.iprintcorehelper_setoptions">IPrintCoreHelper::SetOptions</a>
</dt>
<dt>
<a href="print.iprintcorehelper_whyconstrained">IPrintCoreHelper::WhyConstrained</a>
</dt>
<dt>
<a href="print.iprintcorehelperps_setoptions">IPrintCoreHelperPS::SetOptions</a>
</dt>
<dt>
<a href="print.iprintcorehelperps_whyconstrained">IPrintCoreHelperPS::WhyConstrained</a>
</dt>
<dt>
<a href="print.iprintcorehelperuni_setoptions">IPrintCoreHelperUni::SetOptions</a>
</dt>
<dt>
<a href="print.iprintcorehelperuni_whyconstrained">IPrintCoreHelperUni::WhyConstrained</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PRINT_FEATURE_OPTION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

