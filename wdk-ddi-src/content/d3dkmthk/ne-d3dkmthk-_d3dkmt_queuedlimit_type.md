---
UID : NE:d3dkmthk._D3DKMT_QUEUEDLIMIT_TYPE
title : _D3DKMT_QUEUEDLIMIT_TYPE
author : windows-driver-content
description : The D3DKMT_QUEUEDLIMIT_TYPE enumeration type contains values that indicate the type of operations to set or retrieve the queued limit for in a call to the D3DKMTSetQueuedLimit function.
old-location : display\d3dkmt_queuedlimit_type.htm
old-project : display
ms.assetid : 5e57e2cc-91a2-4150-9805-8a963530080a
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DKMT_QUEUEDLIMIT_TYPE, D3DKMT_QUEUEDLIMIT_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DKMT_QUEUEDLIMIT_TYPE
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
req.typenames : D3DKMT_QUEUEDLIMIT_TYPE
---

# _D3DKMT_QUEUEDLIMIT_TYPE Enumeration
The D3DKMT_QUEUEDLIMIT_TYPE enumeration type contains values that indicate the type of operations to set or retrieve the queued limit for in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetqueuedlimit.md">D3DKMTSetQueuedLimit</a> function.

## Syntax
````
typedef enum _D3DKMT_QUEUEDLIMIT_TYPE { 
  D3DKMT_SET_QUEUEDLIMIT_PRESENT  = 1,
  D3DKMT_GET_QUEUEDLIMIT_PRESENT  = 2
} D3DKMT_QUEUEDLIMIT_TYPE;
````

## Constants

<table>

<tr>
<td>D3DKMT_GET_QUEUEDLIMIT_PRESENT</td>
<td>Indicates to retrieve the limit for the number of present operations that can be queued.</td>
</tr>

<tr>
<td>D3DKMT_SET_QUEUEDLIMIT_PRESENT</td>
<td>Indicates to set the limit for the number of present operations that can be queued.</td>
</tr>
</table>


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
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setqueuedlimit.md">D3DKMT_SETQUEUEDLIMIT</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetqueuedlimit.md">D3DKMTSetQueuedLimit</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_QUEUEDLIMIT_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>