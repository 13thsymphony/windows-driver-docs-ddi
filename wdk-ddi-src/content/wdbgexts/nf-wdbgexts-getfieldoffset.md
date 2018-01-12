---
UID: NF:wdbgexts.GetFieldOffset
title: GetFieldOffset function
author: windows-driver-content
description: The GetFieldOffset function returns the offset of a member from the beginning of a structure.
old-location: debugger\getfieldoffset.htm
old-project: debugger
ms.assetid: 3e5e782b-1a72-446d-9d15-c0f513f3440c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: GetFieldOffset
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
req.alt-api: GetFieldOffset
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
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetFieldOffset function



## -description
The <b>GetFieldOffset</b> function returns the offset of a member from the beginning of a structure.



## -syntax

````
__inline ULONG GetFieldOffset(
  _In_  LPCSTR Type,
  _In_  LPCSTR Field,
  _Out_ PULONG pOffset
);
````


## -parameters

### -param Type [in]

Specifies the name of the type of the structure.  This can be qualified with a module name, for example, <b>mymodule!mystruct</b>.


### -param Field [in]

Specifies the name of the member in the structure.  Submembers can be specified by using a period-separated path, for example, "myfield.mysubfield".


### -param pOffset [out]

Receives the offset of the member from the beginning of an instance of the structure.


## -returns
If the function succeeds, the return value is zero. Otherwise, the return value is an <a href="https://msdn.microsoft.com/41d64bbc-cefe-4665-b054-e6bd135ccd20">IG_DUMP_SYMBOL_INFO error code</a>. 


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