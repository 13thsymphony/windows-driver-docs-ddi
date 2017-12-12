---
UID: NF.wdbgexts.GetTypeSize
title: GetTypeSize function
author: windows-driver-content
description: The GetTypeSize function returns the size in the target's memory of an instance of the specified type.
old-location: debugger\gettypesize.htm
old-project: debugger
ms.assetid: 5532799d-5c3b-41ba-ab62-dca9c9d9eb56
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: GetTypeSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetTypeSize
req.alt-loc: wdbgexts.h
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

# GetTypeSize function



## -description
The <b>GetTypeSize</b> function returns the size in the target's memory of an instance of the specified type.



## -syntax

````
__inline ULONG GetTypeSize(
  _In_ LPCSTR Type
);
````


## -parameters

### -param Type [in]

Specifies the type to return the size of.


## -returns
This function returns the size of an instance of the specified type.


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
<dt>Wdbgexts.h (include Wdbgexts.h or Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>