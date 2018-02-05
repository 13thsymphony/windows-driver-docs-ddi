---
UID : NS:d3dkmthk._D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE
title : "_D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE"
author : windows-driver-content
description : Used to open a protected session from the NT handle.
old-location : display\d3dkmt-openprotectedsessionfromnthandle.htm
old-project : display
ms.assetid : 15937864-c6ef-4c86-b957-87c7afe1cd94
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.d3dkmt-openprotectedsessionfromnthandle, D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE, D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE structure [Display Devices], _D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE, d3dkmthk/D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmthk.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE
---

# _D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE structure
Used to open a protected session from the NT handle.

## Syntax
````
typedef struct _D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE {
  HANDLE        hNtHandle;
  D3DKMT_HANDLE hHandle;
} D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE;
````

## Members


`hHandle`

The protected kernel session handle.

`hNtHandle`

The protected NT session handle.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |