---
UID : NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032
title : D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032
author : windows-driver-content
description : The command list functions for video processing.
old-location : display\d3d12ddi-command-list-funcs-video-process-0032.htm
old-project : display
ms.assetid : c49f79cc-6ceb-4379-94ac-983b897d198b
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032 structure [Display Devices], d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032, D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032, display.d3d12ddi-command-list-funcs-video-process-0032
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d12umddi.h
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
req.typenames : D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032
---

# D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032 structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The command list functions for video processing.

## Syntax
````
typedef struct _D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032 {
  PFND3D12DDI_CLOSECOMMANDLIST                  pfnCloseCommandList;
  PFND3D12DDI_RESETCOMMANDLIST                  pfnResetCommandList;
  PFND3D12DDI_DISCARD_RESOURCE_0003             pfnDiscardResource;
  PFND3D12DDI_SET_MARKER                        pfnSetMarker;
  PFND3D12DDI_SET_PREDICATION                   pfnSetPredication;
  PFND3D12DDI_BEGIN_END_QUERY_0003              pfnBeginQuery;
  PFND3D12DDI_BEGIN_END_QUERY_0003              pfnEndQuery;
  PFND3D12DDI_RESOLVE_QUERY_DATA                pfnResolveQueryData;
  PFND3D12DDI_RESOURCEBARRIER_0022              pfnResourceBarrier;
  PFND3D12DDI_VIDEO_PROCESS_FRAME_0032          pfnProcessFrame;
  PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030  pfnSetProtectedResourceSession;
  PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032         pfnWriteBufferImmediate;
} D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032, D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_PROCESS_0032;
````

## Members


`pfnBeginQuery`

Begin query.

`pfnCloseCommandList`

Close command list.

`pfnDiscardResource`

Discard resource.

`pfnEndQuery`

End query.

`pfnProcessFrame`

Decode frame.

`pfnResetCommandList`

Reset command list.

`pfnResolveQueryData`

Resolve query data.

`pfnResourceBarrier`

Resource barrier.

`pfnSetMarker`

Set marker.

`pfnSetPredication`

Set predication.

`pfnSetProtectedResourceSession`

Set protected resource session.

`pfnWriteBufferImmediate`

Write buffer immediate.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |