---
UID: NS.D3DKMTHK._D3DKMT_CREATEPROTECTEDSESSION
title: _D3DKMT_CREATEPROTECTEDSESSION
author: windows-driver-content
description: Used to create a protected session.
old-location: display\d3dkmt-createprotectedsession.htm
old-project: display
ms.assetid: 4ec42f5a-df33-4da3-a959-64cb400f3177
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_CREATEPROTECTEDSESSION, D3DKMT_CREATEPROTECTEDSESSION
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
req.alt-api: D3DKMT_CREATEPROTECTEDSESSION
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

# _D3DKMT_CREATEPROTECTEDSESSION structure



## -description
Used to create a protected session.


## -syntax

````
typedef struct _D3DKMT_CREATEPROTECTEDSESSION {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hSyncObject;
  const VOID    *pPrivateDriverData;
  UINT          PrivateDriverDataSize;
  const VOID    *pPrivateRuntimeData;
  UINT          PrivateRuntimeDataSize;
  D3DKMT_HANDLE hHandle;
} D3DKMT_CREATEPROTECTEDSESSION;
````


## -struct-fields

### -field hDevice

A handle for the device.

### -field hSyncObject

A monitored fence handle associated with the session.

### -field pPrivateDriverData

Private driver data.

### -field PrivateDriverDataSize

Size of private driver data.

### -field pPrivateRuntimeData

Private runtime data.

### -field PrivateRuntimeDataSize

Size of private runtime data.

### -field hHandle

The protected session handle.

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