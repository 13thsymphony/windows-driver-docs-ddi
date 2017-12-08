---
UID: NF.d3dkmthk.D3DKMTExtractBundleObject
title: D3DKMTExtractBundleObject function
author: windows-driver-content
description: Used to extract the bundle object.
old-location: display\d3dkmtextractbundleobject.htm
old-project: display
ms.assetid: f3193d5b-084f-4df1-9688-26ba5a964cca
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: D3DKMTExtractBundleObject
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
req.alt-api: D3DKMTExtractBundleObject
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

# D3DKMTExtractBundleObject function



## -description

			
            Used to extract the bundle object.


## -syntax

````
NTSTATUS  D3DKMTExtractBundleObject(
  _Inout_ D3DKMT_EXTRACTBUNDLEOBJECT  *D3dkmt_extractbundleobject
);
````


## -parameters

### -param D3dkmt_extractbundleobject [in, out]

Holds information to extract the bundle object.

## -returns
Returns STATUS_SUCCESS if completed successfully. 

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