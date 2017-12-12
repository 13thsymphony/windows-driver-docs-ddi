---
UID: NS.1394._IRB_REQ_ISOCH_FREE_RESOURCES
title: _IRB_REQ_ISOCH_FREE_RESOURCES
author: windows-driver-content
description: This structure contains the fields necessary to carry out a IsochFreeResources request.
old-location: ieee\irb_req_isoch_free_resources.htm
old-project: IEEE
ms.assetid: 28699952-FC15-46A2-96EC-F5F8BD2391D7
ms.author: windowsdriverdev
ms.date: 11/29/2017
ms.keywords: _IRB_REQ_ISOCH_FREE_RESOURCES, IRB_REQ_ISOCH_FREE_RESOURCES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IRB_REQ_ISOCH_FREE_RESOURCES
req.alt-loc: 1394.h
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

# _IRB_REQ_ISOCH_FREE_RESOURCES structure



## -description
This structure contains the fields necessary to carry out a IsochFreeResources request.



## -syntax

````
typedef struct _IRB_REQ_ISOCH_FREE_RESOURCES {
  HANDLE hResource;
} IRB_REQ_ISOCH_FREE_RESOURCES;
````


## -struct-fields

### -field hResource

Specifies the resource handle to release. 


## -remarks
The bus driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS on success. All isochronous buffers that were attached to this resource must be detached prior to issuing this call. If a device driver attempts to free a resource handle with isochronous buffers still attached to it, the handle is not freed and the bus driver returns STATUS_ACCESS_DENIED instead.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>1394.h</dt>
</dl>
</td>
</tr>
</table>