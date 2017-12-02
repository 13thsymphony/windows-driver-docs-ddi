---
UID: NS.engextcpp.ExtKnownStruct
title: ExtKnownStruct
author: windows-driver-content
description: The ExtKnownStruct structure is used to specify how a target's structure can be formatted for output.
old-location: debugger\extknownstruct.htm
old-project: debugger
ms.assetid: 95bf9a47-e121-4432-a28f-5476467f1823
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: ExtKnownStruct,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExtKnownStruct
req.alt-loc: Engextcpp.hpp
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
req.iface: 
---

# ExtKnownStruct structure



## -description
<p>The <b>ExtKnownStruct</b> structure is used to specify how a target's structure can be formatted for output.</p>


## -syntax

````
struct ExtKnownStruct {
  PCSTR                TypeName;
  ExtKnownStructMethod Method;
  bool                 SuppressesTypeName;
};
````


## -struct-fields
<dl>

### -field TypeName

<dd>
<p>The name of the structure type.</p>
</dd>

### -field Method

<dd>
<p>The <a href="debugger.extknownstructmethod">ExtKnownStructMethod</a> callback function that can be called to format an instance of the structure specified in <b>TypeName</b>.</p>
</dd>

### -field SuppressesTypeName

<dd>
<p>A Boolean flag that specifies whether the formatted output includes the name of the structure's type.  If <b>FALSE</b>, the name is included in the formatted output; otherwise, the name is not included.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Engextcpp.hpp (include Engextcpp.hpp)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="debugger.extknownstructmethod">ExtKnownStructMethod</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtKnownStruct structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
