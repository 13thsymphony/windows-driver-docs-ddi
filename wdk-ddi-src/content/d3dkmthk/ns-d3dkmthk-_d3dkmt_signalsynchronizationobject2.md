---
UID : NS:d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2
title : "_D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2"
author : windows-driver-content
description : The D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure contains information about the synchronization events that the D3DKMTSignalSynchronizationObject2 function signals.
old-location : display\d3dkmt_signalsynchronizationobject2.htm
old-project : display
ms.assetid : a4bdafeb-310a-4ceb-966e-a1e3660fc5f2
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2, D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure [Display Devices], D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2, display.d3dkmt_signalsynchronizationobject2, OpenGL_Structs_ac490d8c-5ab9-4a1f-8908-5c2e7786b65b.xml, _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Windows
req.target-min-winverclnt : D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 is supported beginning with the Windows 7 operating system.
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
req.typenames : D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2
---

# _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure
The D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure contains information about the synchronization events that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobject2.md">D3DKMTSignalSynchronizationObject2</a> function signals.

## Syntax
````
typedef struct _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 {
  D3DKMT_HANDLE        hContext;
  UINT                 ObjectCount;
  D3DKMT_HANDLE        ObjectHandleArray[D3DDDI_MAX_OBJECT_SIGNALED];
  D3DDDICB_SIGNALFLAGS Flags;
  ULONG                BroadcastContextCount;
  D3DKMT_HANDLE        BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
  union {
    struct {
      UINT64 FenceValue;
    } Fence;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
    HANDLE CpuEventHandle;
#endif 
    UINT64 Reserved[8];
  };
} D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2;
````

## Members


`BroadcastContext`

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the additional contexts to broadcast the event to. The D3DDDI_MAX_BROADCAST_CONTEXT constant, which is defined as 64, defines the maximum number of contexts that the OpenGL ICD can broadcast the event to.

The original context that the <b>hContext</b> member specifies and that owns the event is not an element in the <b>BroadcastContext</b> array. For example, if the <b>BroadcastContext</b> array contains one element, the OpenGL ICD sends the event to the owning context (<b>hContext</b>) and broadcasts to that one additional context.

`BroadcastContextCount`

[in] The number of additional contexts in the array that <b>BroadcastContext</b> specifies.

`Flags`

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_signalflags.md">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.

`hContext`

[in] A kernel-mode handle to a context that signals the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies.

`ObjectCount`

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array.

`ObjectHandleArray`

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member signals. The D3DDDI_MAX_OBJECT_SIGNALED constant, which is defined as 32, indicates the maximum number of synchronization events that the context can signal.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 is supported beginning with the Windows 7 operating system. D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 is supported beginning with the Windows 7 operating system. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobject2.md">D3DKMTSignalSynchronizationObject2</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_signalflags.md">D3DDDICB_SIGNALFLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>