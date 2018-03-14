---
UID: NF:d3dkmthk.D3DKMTCheckSharedResourceAccess
title: D3DKMTCheckSharedResourceAccess function
author: windows-driver-content
description: The D3DKMTCheckSharedResourceAccess function determines if a process can access a shared resource.
old-location: display\d3dkmtchecksharedresourceaccess.htm
old-project: display
ms.assetid: ca1861d3-a838-4b4a-9304-e75dcca04f0d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTCheckSharedResourceAccess, D3DKMTCheckSharedResourceAccess callback function [Display Devices], OpenGL_Functions_b9ffd997-0bfe-47ad-a769-c2ed8148fe4b.xml, PFND3DKMT_CHECKSHAREDRESOURCEACCESS, d3dkmthk/D3DKMTCheckSharedResourceAccess, display.d3dkmtchecksharedresourceaccess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTCheckSharedResourceAccess is supported beginning with the Windows 7 operating system.
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
-	d3dkmthk.h
api_name:
-	D3DKMTCheckSharedResourceAccess
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTCheckSharedResourceAccess function
The <b>D3DKMTCheckSharedResourceAccess</b> function determines if a process can access a shared resource.

## Syntax

````
NTSTATUS APIENTRY D3DKMTCheckSharedResourceAccess(
  _In_ const D3DKMT_CHECKSHAREDRESOURCEACCESS *pData
);
````

## Parameters

`D3DKMT_CHECKSHAREDRESOURCEACCESS`

TBD


## Return Value

<b>D3DKMTCheckSharedResourceAccess</b> returns one of the following values:

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
The shared resource can be accessed by the process. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DKMTCheckSharedResourceAccess is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_checksharedresourceaccess.md">D3DKMT_CHECKSHAREDRESOURCEACCESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_CHECKSHAREDRESOURCEACCESS callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>