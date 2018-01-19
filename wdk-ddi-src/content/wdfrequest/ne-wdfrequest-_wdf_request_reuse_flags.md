---
UID : NE:wdfrequest._WDF_REQUEST_REUSE_FLAGS
title : _WDF_REQUEST_REUSE_FLAGS
author : windows-driver-content
description : The WDF_REQUEST_REUSE_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_REUSE_PARAMS structure.
old-location : wdf\wdf_request_reuse_flags.htm
old-project : wdf
ms.assetid : 3d1f8f38-b875-4661-9941-4dec28b7e8fb
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDF_REQUEST_REUSE_FLAGS, WDF_REQUEST_REUSE_FLAGS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wdfrequest.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.alt-api : WDF_REQUEST_REUSE_FLAGS
req.alt-loc : wdfrequest.h
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
req.typenames : WDF_REQUEST_REUSE_FLAGS
req.product : Windows 10 or later.
---

# _WDF_REQUEST_REUSE_FLAGS Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_REUSE_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a> structure.

## Syntax
````
typedef enum _WDF_REQUEST_REUSE_FLAGS { 
  WDF_REQUEST_REUSE_NO_FLAGS     = 0x00000000,
  WDF_REQUEST_REUSE_SET_NEW_IRP  = 0x00000001
} WDF_REQUEST_REUSE_FLAGS;
````

## Constants

<table>

<tr>
<td>WDF_REQUEST_REUSE_NO_FLAGS</td>
<td>No flags are set.</td>
</tr>

<tr>
<td>WDF_REQUEST_REUSE_SET_NEW_IRP</td>
<td>The <b>NewIrp</b> member of the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a> structure is valid.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |

## See Also

<dl>
<dt>
<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_REUSE_FLAGS enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>