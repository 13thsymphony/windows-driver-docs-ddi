---
UID: NS:d3dkmthk._D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY
title: _D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY
author: windows-driver-content
description: Describes parameters for an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts.
old-location: display\d3dkmt_setcontextinprocessschedulingpriority.htm
old-project: display
ms.assetid: 3e016793-8c31-4349-a8f5-e5a0cb3b353e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY, D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY
req.alt-loc: D3dkmthk.h
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
req.typenames: D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY
---

# _D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY structure



## -description
Describes parameters for an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts.



## -syntax

````
typedef struct _D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY {
  D3DKMT_HANDLE hContext;
  INT           Priority;
} D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY;
````


## -struct-fields

### -field hContext

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device context that scheduling priority is set on.


### -field Priority

[in] The priority level to set for the device context relative to other device contexts within the same process. 

A value of zero indicates that the context is scheduled with the same priority as other contexts within the same process.

A value of 1 indicates that the context is scheduled ahead of other contexts within the same process.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>