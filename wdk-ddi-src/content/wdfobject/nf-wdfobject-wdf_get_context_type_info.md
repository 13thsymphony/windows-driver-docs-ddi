---
UID: NF.wdfobject.WDF_GET_CONTEXT_TYPE_INFO
title: WDF_GET_CONTEXT_TYPE_INFO macro
author: windows-driver-content
description: This macro is reserved for internal use only.
old-location: wdf\wdf_get_context_type_info.htm
old-project: wdf
ms.assetid: 3273a4b6-9c5e-4671-be9e-45cdd010558a
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WDF_GET_CONTEXT_TYPE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdfobject.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDF_GET_CONTEXT_TYPE_INFO
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# WDF_GET_CONTEXT_TYPE_INFO macro



## -description
This macro is reserved for internal use only.



## -syntax

````
void WDF_GET_CONTEXT_TYPE_INFO(
    _contexttype
);
````


## -parameters

### -param _contexttype 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfobject.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
</table>