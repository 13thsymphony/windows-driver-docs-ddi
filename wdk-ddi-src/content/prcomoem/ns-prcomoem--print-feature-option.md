---
UID: NS.prcomoem._PRINT_FEATURE_OPTION
title: PRINT_FEATURE_OPTION
author: windows-driver-content
description: The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature.
old-location: print\print_feature_option.htm
ms.assetid: 82c9c54b-f124-46d7-a3c9-a17fd8028412
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: print
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
ms.keywords: PRINT_FEATURE_OPTION, PRINT_FEATURE_OPTION
req.iface: IPrintOemUni3
req.product: Windows 10 or later.
---

# PRINT_FEATURE_OPTION structure



## -description
<p>The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature.</p>


## -syntax

````
typedef struct _PRINT_FEATURE_OPTION {
  PCSTR pszFeature;
  PCSTR pszOption;
} PRINT_FEATURE_OPTION;
````


## -struct-fields
<dl>

### -field <b>pszFeature</b>

<dd>
<p>The printing feature.</p>
</dd>

### -field <b>pszOption</b>

<dd>
<p>One of the options for the printing feature.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by methods that belong to the <b>IPrintCoreHelper</b>, <b>IPrintCoreHelperPS</b>, and <b>IPrintCoreHelperUni</b> interfaces. The methods are listed in the See Also section.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552963">IPrintCoreHelper::SetOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552965">IPrintCoreHelper::WhyConstrained</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552912">IPrintCoreHelperPS::SetOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552915">IPrintCoreHelperPS::WhyConstrained</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552945">IPrintCoreHelperUni::SetOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552947">IPrintCoreHelperUni::WhyConstrained</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PRINT_FEATURE_OPTION structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
