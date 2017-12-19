---
UID: NS.D3DKMDDI._DXGKARG_DESTROYPERIODICFRAMENOTIFICATION
title: _DXGKARG_DESTROYPERIODICFRAMENOTIFICATION
author: windows-driver-content
description: The arguments used to destroy a periodic frame notification.
old-location: display\dxgkarg_destroyperiodicframenotification.htm
old-project: display
ms.assetid: 94797515-3440-46A9-ACBD-09D005A33CE3
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGKARG_DESTROYPERIODICFRAMENOTIFICATION, DXGKARG_DESTROYPERIODICFRAMENOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_DESTROYPERIODICFRAMENOTIFICATION
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _DXGKARG_DESTROYPERIODICFRAMENOTIFICATION structure



## -description
The arguments used to destroy a periodic frame notification.



## -syntax

````
typedef struct _DXGKARG_DESTROYPERIODICFRAMENOTIFICATION {
  HANDLE hNotification;
  HANDLE hAdapter;
} DXGKARG_DESTROYPERIODICFRAMENOTIFICATION;
````


## -struct-fields

### -field hNotification

A handle to the notification object created by the KMD.


### -field hAdapter

A handle to the adapter that the notification object was created for.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>