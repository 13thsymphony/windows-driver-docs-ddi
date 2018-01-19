---
UID : NS:d3dkmthk._D3DKMT_CREATEHWCONTEXT
title : _D3DKMT_CREATEHWCONTEXT
author : windows-driver-content
description : A structure holding information to create a hardware context.
old-location : display\d3dkmt_createhwcontext.htm
old-project : display
ms.assetid : 9B6EA552-B576-45F3-A0BD-7EB721638D7F
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DKMT_CREATEHWCONTEXT, D3DKMT_CREATEHWCONTEXT
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
req.alt-api : D3DKMT_CREATEHWCONTEXT
req.alt-loc : d3dkmthk.h
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
req.typenames : D3DKMT_CREATEHWCONTEXT
---

# _D3DKMT_CREATEHWCONTEXT structure
A structure holding information to create a hardware context.

## Syntax
````
typedef struct _D3DKMT_CREATEHWCONTEXT {
  D3DKMT_HANDLE               hDevice;
  UINT                        NodeOrdinal;
  UINT                        EngineAffinity;
  D3DDDI_CREATEHWCONTEXTFLAGS Flags;
  UINT                        PrivateDriverDataSize;
  VOID                        * pPrivateDriverData;
  D3DKMT_HANDLE               hHwContext;
} D3DKMT_CREATEHWCONTEXT;
````

## Members

        
            `EngineAffinity`

            Engine affinity within the specified node.
        
            `Flags`

            Context creation flags.
        
            `hDevice`

            Handle to the device owning this context.
        
            `hHwContext`

            Handle of the created context.
        
            `NodeOrdinal`

            Identifier for the node targetted by this context.
        
            `PrivateDriverDataSize`

            Size of private driver data.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h |