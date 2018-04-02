---
UID: NS:d3dkmthk._D3DKMT_CREATEPROTECTEDSESSION
title: "_D3DKMT_CREATEPROTECTEDSESSION"
author: windows-driver-content
description: Used to create a protected session.
old-location: display\d3dkmt-createprotectedsession.htm
old-project: display
ms.assetid: 4ec42f5a-df33-4da3-a959-64cb400f3177
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_CREATEPROTECTEDSESSION, D3DKMT_CREATEPROTECTEDSESSION structure [Display Devices], _D3DKMT_CREATEPROTECTEDSESSION, d3dkmthk/D3DKMT_CREATEPROTECTEDSESSION, display.d3dkmt-createprotectedsession
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_CREATEPROTECTEDSESSION
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_CREATEPROTECTEDSESSION
---

# _D3DKMT_CREATEPROTECTEDSESSION structure
Used to create a protected session.

## Syntax
```
typedef struct _D3DKMT_CREATEPROTECTEDSESSION {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hSyncObject;
  CONST VOID    *pPrivateDriverData;
  UINT          PrivateDriverDataSize;
  CONST VOID    *pPrivateRuntimeData;
  UINT          PrivateRuntimeDataSize;
  D3DKMT_HANDLE hHandle;
} D3DKMT_CREATEPROTECTEDSESSION;
```

## Members


`hDevice`

A handle for the device.

`hSyncObject`

A monitored fence handle associated with the session.

`pPrivateDriverData`

Private driver data.

`PrivateDriverDataSize`

Size of private driver data.

`pPrivateRuntimeData`

Private runtime data.

`PrivateRuntimeDataSize`

Size of private runtime data.

`hHandle`

The protected session handle.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |