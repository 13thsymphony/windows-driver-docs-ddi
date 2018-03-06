---
UID: NC:d3dkmthk.PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
title: PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
author: windows-driver-content
description: Maps a global NT handle to resource information that is needed for a call to the D3DKMTQueryResourceInfo function.
old-location: display\d3dkmtqueryresourceinfofromnthandle.htm
old-project: display
ms.assetid: 7a433aaf-3215-4d11-8989-2d7bdc7f7499
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTQueryResourceInfoFromNtHandle, D3DKMTQueryResourceInfoFromNtHandle callback function [Display Devices], PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE, d3dkmthk/D3DKMTQueryResourceInfoFromNtHandle, display.d3dkmtqueryresourceinfofromnthandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMTQueryResourceInfoFromNtHandle
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---


# PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE callback function
Maps a global NT handle  to resource information that is needed for a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryresourceinfo.md">D3DKMTQueryResourceInfo</a> function.

## Syntax

```
PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE Pfnd3dkmtQueryresourceinfofromnthandle;

NTSTATUS Pfnd3dkmtQueryresourceinfofromnthandle(
  D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE *
)
{...}
```

## Parameters

`*`




## Return Value

Returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The mapping was performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">

         Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryresourceinfo.md">D3DKMTQueryResourceInfo</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryresourceinfofromnthandle.md">D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>