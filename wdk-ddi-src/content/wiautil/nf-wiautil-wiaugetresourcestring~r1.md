---
UID: NF.wiautil.wiauGetResourceString~r1
title: wiauGetResourceString function
author: windows-driver-content
description: The wiauGetResourceString function gets a resource string, storing it as a BSTR.
old-location: image\wiaugetresourcestring.htm
old-project: image
ms.assetid: b042702a-46ff-4ec9-8a92-af8516802e64
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: wiauGetResourceString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: wiauGetResourceString
req.alt-loc: wiautil.h
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

# wiauGetResourceString function



## -description
The <b>wiauGetResourceString</b> function gets a resource string, storing it as a <b>BSTR</b>.


## -syntax

````
HRESULT _stdcall wiauGetResourceString(
        HINSTANCE hInst,
        LONG      lResourceID,
  _Out_ BSTR      *pbstrStr
);
````


## -parameters

### -param hInst 

Specifies the handle of the module instance.

### -param lResourceID 

Specifies the resource ID of the target BSTR value.

### -param pbstrStr [out]

Points to the memory location that receives the retrieved string. The caller of this function must free this string by calling <b>SysFreeString</b> (described in the Microsoft Windows SDK documentation).

## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error.

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
Version
</th>
<td width="70%">
Available in Windows XP and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wiautil.h (include Wiautil.h)</dt>
</dl>
</td>
</tr>
</table>