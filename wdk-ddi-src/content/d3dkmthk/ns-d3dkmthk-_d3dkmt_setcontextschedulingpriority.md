---
UID : NS:d3dkmthk._D3DKMT_SETCONTEXTSCHEDULINGPRIORITY
title : _D3DKMT_SETCONTEXTSCHEDULINGPRIORITY
author : windows-driver-content
description : The D3DKMT_SETCONTEXTSCHEDULINGPRIORITY structure describes parameters for setting scheduling priority for a device context.
old-location : display\d3dkmt_setcontextschedulingpriority.htm
old-project : display
ms.assetid : 879c7117-080a-4056-b94f-6462b370f434
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DKMT_SETCONTEXTSCHEDULINGPRIORITY, D3DKMT_SETCONTEXTSCHEDULINGPRIORITY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DKMT_SETCONTEXTSCHEDULINGPRIORITY
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
req.typenames : D3DKMT_SETCONTEXTSCHEDULINGPRIORITY
---

# _D3DKMT_SETCONTEXTSCHEDULINGPRIORITY structure
The D3DKMT_SETCONTEXTSCHEDULINGPRIORITY structure describes parameters for setting scheduling priority for a device context.

## Syntax
````
typedef struct _D3DKMT_SETCONTEXTSCHEDULINGPRIORITY {
  D3DKMT_HANDLE hContext;
  INT           Priority;
} D3DKMT_SETCONTEXTSCHEDULINGPRIORITY;
````

## Members

        
            `hContext`

            [in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device context that scheduling priority is set on.
        
            `Priority`

            [in] The priority level to set for the device context.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetcontextschedulingpriority.md">D3DKMTSetContextSchedulingPriority</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SETCONTEXTSCHEDULINGPRIORITY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>