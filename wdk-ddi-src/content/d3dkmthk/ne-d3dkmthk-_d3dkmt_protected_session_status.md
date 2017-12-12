---
UID: NE.d3dkmthk._D3DKMT_PROTECTED_SESSION_STATUS
title: _D3DKMT_PROTECTED_SESSION_STATUS
author: windows-driver-content
description: Indicates the status of the protected session.
old-location: display\d3dkmt-protected-session-status.htm
old-project: display
ms.assetid: 87a7de73-5e94-4016-b760-f3501ead08ac
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMT_PROTECTED_SESSION_STATUS, D3DKMT_PROTECTED_SESSION_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_PROTECTED_SESSION_STATUS
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

# _D3DKMT_PROTECTED_SESSION_STATUS enumeration



## -description
Indicates the status of the protected session.



## -syntax

````
typedef enum _D3DKMT_PROTECTED_SESSION_STATUS { 
  D3DKMT_PROTECTED_SESSION_STATUS_OK       = 0,
  D3DKMT_PROTECTED_SESSION_STATUS_INVALID  = 1
} D3DKMT_PROTECTED_SESSION_STATUS;
````


## -enum-fields

### -field D3DKMT_PROTECTED_SESSION_STATUS_OK

Indicates that the status is okay.


### -field D3DKMT_PROTECTED_SESSION_STATUS_INVALID

Indicates that the status is invalid.


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