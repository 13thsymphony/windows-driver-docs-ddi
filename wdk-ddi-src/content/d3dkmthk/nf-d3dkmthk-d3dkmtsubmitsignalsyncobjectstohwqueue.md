---
UID: NF:d3dkmthk.D3DKMTSubmitSignalSyncObjectsToHwQueue
title: D3DKMTSubmitSignalSyncObjectsToHwQueue function
author: windows-driver-content
description: Used to submit a signal to the hardware queue.
old-location: display\d3dkmtsubmitsignalsyncobjectstohwqueue.htm
old-project: display
ms.assetid: DA0D44AF-168F-4B9B-B184-1DC8C3477CBC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTSubmitSignalSyncObjectsToHwQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTSubmitSignalSyncObjectsToHwQueue
req.alt-loc: tbd
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Tbd
req.dll: Tbd
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTSubmitSignalSyncObjectsToHwQueue function



## -description
Used to submit a signal to the hardware queue.



## -syntax

````
NTSTATUS APIENTRY D3DKMTSubmitSignalSyncObjectsToHwQueue(
  _In_ const D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE *submitWaitForSyncObjectsToHwQueue
);
````


## -parameters

### -param submitWaitForSyncObjectsToHwQueue [in]

A structure holding the information needed to submit a signal to the hardware queue.


## -returns
Returns STATUS_SUCCESS if called successfully. 


## -remarks


## -requirements
<table>
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
Library

</th>
<td width="70%">
<dl>
<dt>Tbd</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Tbd</dt>
</dl>
</td>
</tr>
</table>