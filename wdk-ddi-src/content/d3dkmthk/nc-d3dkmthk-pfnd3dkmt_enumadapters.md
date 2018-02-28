---
UID: NC:d3dkmthk.PFND3DKMT_ENUMADAPTERS
title: PFND3DKMT_ENUMADAPTERS
author: windows-driver-content
description: Enumerates all graphics adapters on the system.
old-location: display\d3dkmtenumadapters.htm
old-project: display
ms.assetid: 07c0aeac-0f82-492a-aa98-0ba5a962b9cf
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMTEnumAdapters, D3DKMTEnumAdapters callback function [Display Devices], PFND3DKMT_ENUMADAPTERS, d3dkmthk/D3DKMTEnumAdapters, display.d3dkmtenumadapters
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
-	D3DKMTEnumAdapters
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---


# PFND3DKMT_ENUMADAPTERS callback function
Enumerates all graphics adapters on the system.

## Syntax

```
PFND3DKMT_ENUMADAPTERS Pfnd3dkmtEnumadapters;

NTSTATUS Pfnd3dkmtEnumadapters(
  CONST D3DKMT_ENUMADAPTERS *
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
The enumeration was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">
The  <i>pEnumAdapters</i> parameter was validated and determined to be incorrect.


</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.

## Remarks

The operating system enumerates graphics adapters in the same sequence as their corresponding physical devices.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_enumadapters.md">D3DKMT_ENUMADAPTERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_ENUMADAPTERS callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>