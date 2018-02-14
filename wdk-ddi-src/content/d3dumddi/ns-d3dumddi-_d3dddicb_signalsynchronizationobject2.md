---
UID: NS:d3dumddi._D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2
title: "_D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2"
author: windows-driver-content
description: Describes the parameters that are required to set up signaling in a call to the pfnSignalSynchronizationObject2Cb function.
old-location: display\d3dddicb_signalsynchronizationobject2.htm
old-project: display
ms.assetid: cb8df28d-1d44-446b-83a8-b4191213973d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2 structure [Display Devices], display.d3dddicb_signalsynchronizationobject2, _D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2, D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2, d3dumddi/D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dumddi.h
apiname:
-	D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2
product: Windows
targetos: Windows
req.typenames: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2
---

# _D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2 structure
Describes the parameters that are required to set up signaling in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> function.

## Syntax
````
typedef struct _D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2 {
  HANDLE               hContext;
  UINT                 ObjectCount;
  D3DKMT_HANDLE        ObjectHandleArray[D3DDDI_MAX_OBJECT_SIGNALED];
  D3DDDICB_SIGNALFLAGS Flags;
  ULONG                BroadcastContextCount;
  D3DKMT_HANDLE        BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
  union {
    UINT64 FenceValue;
    HANDLE CpuEventHandle;
  };
} D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2;
````

## Members


`BroadcastContext`

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent kernel-mode handles to the additional contexts to broadcast the current signal command to. The <b>D3DDDI_MAX_BROADCAST_CONTEXT</b> constant, which is defined as 64, defines the maximum number of synchronization events that the context can signal to.

All contexts must be created for the same Direct3D device and the context that is specified by <b>hContext</b>.

`BroadcastContextCount`

[in] The number of contexts to broadcast this signal buffer to.

`Flags`

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_signalflags.md">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.

`hContext`

[in] A handle to a Direct3D context that signals the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies.

`ObjectCount`

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array.

`ObjectHandleArray`

[in] An array of handles to the synchronization events that the context that is specified by the <b>hContext</b> member signals. The <b>D3DDDI_MAX_OBJECT_SIGNALED</b> constant, which is defined as 32, indicates the maximum number of synchronization events that the context can signal.

All synchronization objects must be created on the same logical adapter as the  context specified by <b>hContext</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_signalflags.md">D3DDDICB_SIGNALFLAGS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>