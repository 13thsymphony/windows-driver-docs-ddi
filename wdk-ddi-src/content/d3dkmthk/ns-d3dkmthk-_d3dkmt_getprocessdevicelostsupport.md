---
UID: NS.D3DKMTHK._D3DKMT_GETPROCESSDEVICELOSTSUPPORT
title: _D3DKMT_GETPROCESSDEVICELOSTSUPPORT
author: windows-driver-content
description: Used to get the indicated process.
old-location: display\d3dkmt-getprocessdevicelostsupport.htm
old-project: display
ms.assetid: 726a4f12-3cee-4d95-89d3-39f2bb357967
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_GETPROCESSDEVICELOSTSUPPORT, D3DKMT_GETPROCESSDEVICELOSTSUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_GETPROCESSDEVICELOSTSUPPORT
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

# _D3DKMT_GETPROCESSDEVICELOSTSUPPORT structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Used to get the indicated process.



## -syntax

````
typedef struct _D3DKMT_GETPROCESSDEVICELOSTSUPPORT {
  HANDLE  hProcess;
  LUID    AdapterLuid;
  BOOLEAN Support;
} D3DKMT_GETPROCESSDEVICELOSTSUPPORT;
````


## -struct-fields

### -field hProcess

A handle to the process.


### -field AdapterLuid

LUID of Adapter that is potentially being detached


### -field Support

Indicates whether or not all devices of the process using the adapter can recover from graphics device lost.


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
</table>