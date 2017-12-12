---
UID: NS.D3DKMTHK._D3DKMT_PRESENT_REDIRECTED
title: _D3DKMT_PRESENT_REDIRECTED
author: windows-driver-content
description: Used to give information on the status of the present history token.
old-location: display\d3dkmt-present-redirected.htm
old-project: display
ms.assetid: a883d80a-0240-4a2a-b3d8-ca87080717ee
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMT_PRESENT_REDIRECTED, D3DKMT_PRESENT_REDIRECTED
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
req.alt-api: D3DKMT_PRESENT_REDIRECTED
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

# _D3DKMT_PRESENT_REDIRECTED structure



## -description
Used to give information on the status of the present history token.



## -syntax

````
typedef struct _D3DKMT_PRESENT_REDIRECTED {
  D3DKMT_HANDLE                   hSyncObj;
  ULONGLONG                       WaitedFenceValue;
  D3DKMT_PRESENTHISTORYTOKEN      PresentHistoryToken;
  D3DKMT_PRESENT_REDIRECTED_FLAGS Flags;
} D3DKMT_PRESENT_REDIRECTED;
````


## -struct-fields

### -field hSyncObj

The sync object that the PHT waits on.


### -field WaitedFenceValue

The fence value of hSyncObj that PHT waits on


### -field PresentHistoryToken

The present history token.


### -field Flags

The flags needed to give the status of the present history token.


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