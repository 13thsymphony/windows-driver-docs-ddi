---
UID: NF.hbaapi.HBA_GetNumberOfAdapters
title: HBA_GetNumberOfAdapters function
author: windows-driver-content
description: The HBA_GetNumberOfAdapters routine returns the number of HBAs supported by the library.
old-location: storage\hba_getnumberofadapters.htm
old-project: storage
ms.assetid: 5864a535-4ff8-4c9a-abf9-f835c7fde305
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: HBA_GetNumberOfAdapters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_GetNumberOfAdapters
req.alt-loc: Hbaapi.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
---

# HBA_GetNumberOfAdapters function



## -description
The <b>HBA_GetNumberOfAdapters</b> routine returns the number of HBAs supported by the library. 



## -syntax

````
HBA_UINT32 HBA_API HBA_GetNumberOfAdapters(void);
````


## -parameters


## -returns
The <b>HBA_GetNumberOfAdapters</b> routine returns the number of adapters supported by this library. If no adapters are supported, <b>HBA_GetNumberOfAdapters</b> returns 0.

The <b>HBA_GetNumberOfAdapters</b> routine returns the number of adapters supported by this library. If no adapters are supported, <b>HBA_GetNumberOfAdapters</b> returns 0.

The <b>HBA_GetNumberOfAdapters</b> routine returns the number of adapters supported by this library. If no adapters are supported, <b>HBA_GetNumberOfAdapters</b> returns 0.


## -remarks
The <b>HBA_GetNumberOfAdapters</b> routine allows the caller to dynamically determine the size of the HBA inventory without having to restart the system, the HBA drivers, or the library. 


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
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Hbaapi.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Hbaapi.dll</dt>
</dl>
</td>
</tr>
</table>