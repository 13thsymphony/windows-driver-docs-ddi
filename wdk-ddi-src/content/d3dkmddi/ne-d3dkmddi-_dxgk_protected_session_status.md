---
UID: NE:d3dkmddi._DXGK_PROTECTED_SESSION_STATUS
title: _DXGK_PROTECTED_SESSION_STATUS
author: windows-driver-content
description: Used to indicate the status of the current session.
old-location: display\dxgk_protected_session_status.htm
old-project: display
ms.assetid: B6FCA052-FFAE-4F7D-8BDE-CDB84772B5E5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PROTECTED_SESSION_STATUS, DXGK_PROTECTED_SESSION_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_PROTECTED_SESSION_STATUS
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
req.typenames: DXGK_PROTECTED_SESSION_STATUS
---

# _DXGK_PROTECTED_SESSION_STATUS enumeration



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Used to indicate the status of the current session.



## -syntax

````
typedef enum _DXGK_PROTECTED_SESSION_STATUS { 
  DXGK_PROTECTED_SESSION_STATUS_OK       = 0,
  DXGK_PROTECTED_SESSION_STATUS_INVALID  = 1
} DXGK_PROTECTED_SESSION_STATUS;
````


## -enum-fields

### -field DXGK_PROTECTED_SESSION_STATUS_OK

Indicates that the status is okay.


### -field DXGK_PROTECTED_SESSION_STATUS_INVALID

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
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>