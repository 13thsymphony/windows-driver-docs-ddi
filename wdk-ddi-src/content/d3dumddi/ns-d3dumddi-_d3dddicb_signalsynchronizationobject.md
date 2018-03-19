---
UID: NS:d3dumddi._D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT
title: "_D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT"
author: windows-driver-content
description: The D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT structure describes the parameters that are required to set up signaling in a call to the pfnSignalSynchronizationObjectCb function.
old-location: display\d3dddicb_signalsynchronizationobject.htm
old-project: display
ms.assetid: 08fbcc15-f40f-46de-b3ff-603bc1476d97
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT, D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT structure [Display Devices], D3D_param_Structs_347963a7-4c6b-478e-9a2f-e708a807cac6.xml, _D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT, d3dumddi/D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT, display.d3dddicb_signalsynchronizationobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dumddi.h
api_name:
-	D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT
product: Windows
targetos: Windows
req.typenames: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT
---

# _D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT structure
The D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT structure describes the parameters that are required to set up signaling in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a> function.

## Syntax
````
typedef struct _D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT {
  HANDLE               hContext;
  UINT                 ObjectCount;
  D3DKMT_HANDLE        ObjectHandleArray[D3DDDI_MAX_OBJECT_SIGNALED];
  D3DDDICB_SIGNALFLAGS Flags;
} D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT;
````

## Members


`hContext`

[in] A handle to a Direct3D context that signals the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies.

`ObjectCount`

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array.

`ObjectHandleArray`

[in] An array of handles to the synchronization events that the context that is specified by the <b>hContext</b> member signals. The <b>D3DDDI_MAX_OBJECT_SIGNALED</b> constant, which is defined as 32, indicates the maximum number of synchronization events that the context can signal.

`Flags`

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_signalflags.md">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_signalflags.md">D3DDDICB_SIGNALFLAGS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>