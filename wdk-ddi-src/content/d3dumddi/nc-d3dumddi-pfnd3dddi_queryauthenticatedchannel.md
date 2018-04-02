---
UID: NC:d3dumddi.PFND3DDDI_QUERYAUTHENTICATEDCHANNEL
title: PFND3DDDI_QUERYAUTHENTICATEDCHANNEL
author: windows-driver-content
description: The QueryAuthenticatedChannel function queries an authenticated channel for capability and state information.
old-location: display\queryauthenticatedchannel.htm
old-project: display
ms.assetid: 13b65b5a-9512-4d67-b629-479bdd74674e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_QUERYAUTHENTICATEDCHANNEL, QueryAuthenticatedChannel, QueryAuthenticatedChannel callback function [Display Devices], UserModeDisplayDriver_Functions_4d4f5258-9b7c-42c8-b256-223b6b99d1f6.xml, d3dumddi/QueryAuthenticatedChannel, display.queryauthenticatedchannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: QueryAuthenticatedChannel is supported beginning with the Windows 7 operating system.
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	QueryAuthenticatedChannel
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_QUERYAUTHENTICATEDCHANNEL callback function
The <i>QueryAuthenticatedChannel</i> function queries an authenticated channel for capability and state information.

## Syntax

```
PFND3DDDI_QUERYAUTHENTICATEDCHANNEL Pfnd3dddiQueryauthenticatedchannel;

HRESULT Pfnd3dddiQueryauthenticatedchannel(
  HANDLE hDevice,
  CONST D3DDDIARG_QUERYAUTHENTICATEDCHANNEL *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>QueryAuthenticatedChannel</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The authenticated channel is successfully queried. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>QueryAuthenticatedChannel</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>

## Remarks

The input buffer contains the driver's handle to the authenticated channel, a sequence number, and a GUID that indicates the type of query. The driver should fail all queries if the driver did not previously initialize the sequence number through a call to its <a href="https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd">ConfigureAuthenticatedChannel</a> function. The driver should also fail the query if the sequence number is not greater than the sequence number of the previous query call. 

The driver should duplicate the input data in the structure of the output buffer and should sign the output structure identically to how it currently handles <a href="https://msdn.microsoft.com/2c138dbd-55ca-4c71-8c8b-b2efd1ca80f2">Output Protection Manager</a> (OPM) queries.

Except for those situations in which the application incorrectly specifies an output buffer that is too small, the driver should always place the return code in the output structure. Therefore, the application has a secure mechanism to determine the return code. 

<i>QueryAuthenticatedChannel</i> performs different operations depending on each of following GUIDs that is specified in the input structure. The driver should fail if the input and output buffer sizes do not match the sizes that are defined for the specified GUID.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | QueryAuthenticatedChannel is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd">ConfigureAuthenticatedChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543247">D3DDDIARG_QUERYAUTHENTICATEDCHANNEL</a>