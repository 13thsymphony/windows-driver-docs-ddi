---
UID: NF.d3dkmthk.D3DKMTCreateBundleObject
title: D3DKMTCreateBundleObject function
author: windows-driver-content
description: Used to create a bundle object.
old-location: display\d3dkmtcreatebundleobject.htm
old-project: display
ms.assetid: c4d62ccf-606b-457e-a239-1b5189e42657
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3DKMTCreateBundleObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTCreateBundleObject
req.alt-loc: d3dkmthk.h
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
---

# D3DKMTCreateBundleObject function



## -description

			
            Used to create a bundle object.



## -syntax

````
NTSTATUS  D3DKMTCreateBundleObject(
  _Inout_ D3DKMT_CREATEBUNDLEOBJECT  *D3dkmt_createbundleobject
);
````


## -parameters

### -param D3dkmt_createbundleobject [in, out]

Holds information to create a bundle object.


## -returns
Returns STATUS_SUCCESS if the call has been successfully completed.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">


</td>
</tr>
</table>