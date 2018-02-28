---
UID: NS:d3dkmthk._D3DKMT_PRESENT_REDIRECTED
title: "_D3DKMT_PRESENT_REDIRECTED"
author: windows-driver-content
description: Used to give information on the status of the present history token.
old-location: display\d3dkmt-present-redirected.htm
old-project: display
ms.assetid: a883d80a-0240-4a2a-b3d8-ca87080717ee
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_PRESENT_REDIRECTED, D3DKMT_PRESENT_REDIRECTED structure [Display Devices], _D3DKMT_PRESENT_REDIRECTED, d3dkmthk/D3DKMT_PRESENT_REDIRECTED, display.d3dkmt-present-redirected
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
-	D3DKMT_PRESENT_REDIRECTED
product: Windows
targetos: Windows
req.typenames: D3DKMT_PRESENT_REDIRECTED
---

# _D3DKMT_PRESENT_REDIRECTED structure
Used to give information on the status of the present history token.

## Syntax
````
typedef struct _D3DKMT_PRESENT_REDIRECTED {
  D3DKMT_HANDLE                   hSyncObj;
  ULONGLONG                       WaitedFenceValue;
  D3DKMT_PRESENTHISTORYTOKEN      PresentHistoryToken;
  D3DKMT_PRESENT_REDIRECTED_FLAGS Flags;
} D3DKMT_PRESENT_REDIRECTED;
````

## Members


`Flags`

The flags needed to give the status of the present history token.

`hSyncObj`

The sync object that the PHT waits on.

`PresentHistoryToken`

The present history token.

`WaitedFenceValue`

The fence value of hSyncObj that PHT waits on


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |