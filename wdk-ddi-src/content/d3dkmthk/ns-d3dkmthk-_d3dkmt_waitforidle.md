---
UID : NS:d3dkmthk._D3DKMT_WAITFORIDLE
title : _D3DKMT_WAITFORIDLE
author : windows-driver-content
description : The D3DKMT_WAITFORIDLE structure specifies a display device to wait for an idle condition.
old-location : display\d3dkmt_waitforidle.htm
old-project : display
ms.assetid : 0f590f5f-5ffe-4d83-86b0-e8dd0bfa5b8f
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DKMT_WAITFORIDLE, D3DKMT_WAITFORIDLE
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
req.alt-api : D3DKMT_WAITFORIDLE
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
req.typenames : D3DKMT_WAITFORIDLE
---

# _D3DKMT_WAITFORIDLE structure
The D3DKMT_WAITFORIDLE structure specifies a display device to wait for an idle condition.

## Syntax
````
typedef struct _D3DKMT_WAITFORIDLE {
  D3DKMT_HANDLE hDevice;
} D3DKMT_WAITFORIDLE;
````

## Members

        
            `hDevice`

            [in] A handle to the display device.


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
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforidle.md">D3DKMTWaitForIdle</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_WAITFORIDLE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>