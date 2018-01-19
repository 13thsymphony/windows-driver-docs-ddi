---
UID : NS:d3dumddi.D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
title : D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
author : windows-driver-content
description : D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU is used with pfnSignalSynchronizationObjectFromGpuCb to signal a monitored fence.
old-location : display\d3dddicb_signalsynchronizationobjectfromgpu.htm
old-project : display
ms.assetid : FF098E63-842F-4D88-A184-BE886E0ED507
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU, D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
req.alt-loc : d3dumddi.h
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
req.typenames : D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
---

# D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU structure
<b>D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpucb.md">pfnSignalSynchronizationObjectFromGpuCb</a> to signal a monitored fence.

## Syntax
````
typedef struct D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU {
  HANDLE              hContext;
  UINT                ObjectCount;
  const D3DKMT_HANDLE *ObjectHandleArray;
  union {
    const UINT64 *MonitoredFenceValueArray;
    UINT64       Reserved[8];
  };
} D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU;
````

## Members

        
            `hContext`

            [in] A kernel-mode handle to the context stream.
        
            `ObjectCount`

            [in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.
        
            `ObjectHandleArray`

            [in] An array of kernel-mode handles to the synchronization events that the <b>hContext</b> member signals.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpucb.md">pfnSignalSynchronizationObjectFromGpuCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>