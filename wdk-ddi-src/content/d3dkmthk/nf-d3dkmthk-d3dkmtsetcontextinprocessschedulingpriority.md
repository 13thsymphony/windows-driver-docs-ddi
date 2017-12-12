---
UID: NF.d3dkmthk.D3DKMTSetContextInProcessSchedulingPriority
title: D3DKMTSetContextInProcessSchedulingPriority function
author: windows-driver-content
description: Called by an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts.
old-location: display\d3dkmtsetcontextinprocessschedulingpriority.htm
old-project: display
ms.assetid: ebac0d06-53cb-4a84-9af9-f8aa9a6eccb6
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3DKMTSetContextInProcessSchedulingPriority
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTSetContextInProcessSchedulingPriority
req.alt-loc: D3dkmthk.h
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
---

# D3DKMTSetContextInProcessSchedulingPriority function



## -description
Called by an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts.



## -syntax

````
_Check_return_ NTSTATUS APIENTRY D3DKMTSetContextInProcessSchedulingPriority(
  _In_ const D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY *pContextPriority
);
````


## -parameters

### -param pContextPriority [in]

A pointer to a <a href="display.d3dkmt_setcontextinprocessschedulingpriority">D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY</a> structure that describes parameters for setting the scheduling priority for a device context.


## -returns
Returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The scheduling priority was successfully set.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmt_setcontextinprocessschedulingpriority">D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY</a>
</dt>
<dt>
<a href="display.d3dkmtgetcontextinprocessschedulingpriority">D3DKMTGetContextInProcessSchedulingPriority</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSetContextInProcessSchedulingPriority function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

