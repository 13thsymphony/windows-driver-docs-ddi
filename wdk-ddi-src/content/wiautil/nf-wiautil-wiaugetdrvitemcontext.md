---
UID: NF.wiautil.wiauGetDrvItemContext
title: wiauGetDrvItemContext function
author: windows-driver-content
description: The wiauGetDrvItemContext function gets the driver item context, and optionally, the driver item.
old-location: image\wiaugetdrvitemcontext.htm
old-project: Image
ms.assetid: 6d4b7a25-436f-4547-8969-66dd45fa46fd
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: wiauGetDrvItemContext
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
req.alt-api: wiauGetDrvItemContext
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

# wiauGetDrvItemContext function



## -description
The <b>wiauGetDrvItemContext</b> function gets the driver item context, and optionally, the driver item.



## -syntax

````
HRESULT _stdcall wiauGetDrvItemContext(
  _In_    BYTE                  *pWiasContext,
  _Inout_ VOID                  **ppItemCtx,
  _Inout_ IWiaDrvItem ppDrvItem **ppDrvItem
);
````


## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.


### -param ppItemCtx [in, out]

Pointer to a memory location that receives a pointer to the driver item context.


### -param ppDrvItem [in, out]

<i>Optional</i>. Pointer to a memory location that receives a pointer to a driver item. The default value of this parameter is <b>NULL</b>, which means that when this function returns, no change is made to this parameter.


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