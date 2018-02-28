---
UID: NF:d3dkmthk.D3DKMTCheckMonitorPowerState
title: D3DKMTCheckMonitorPowerState function
author: windows-driver-content
description: The D3DKMTCheckMonitorPowerState function verifies the power state of a monitor.
old-location: display\d3dkmtcheckmonitorpowerstate.htm
old-project: display
ms.assetid: 8f218b63-304e-4f25-88d8-ea1326c613ee
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMTCheckMonitorPowerState, D3DKMTCheckMonitorPowerState callback function [Display Devices], OpenGL_Functions_d05a2b63-fe81-45f0-908d-94043416b1d0.xml, PFND3DKMT_CHECKMONITORPOWERSTATE, d3dkmthk/D3DKMTCheckMonitorPowerState, display.d3dkmtcheckmonitorpowerstate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: NtosKrnl.exe
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
-	D3DKMTCheckMonitorPowerState
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTCheckMonitorPowerState function
The <b>D3DKMTCheckMonitorPowerState</b> function verifies the power state of a monitor.

## Syntax

````
NTSTATUS APIENTRY D3DKMTCheckMonitorPowerState(
  _In_ const D3DKMT_CHECKMONITORPOWERSTATE *pData
);
````

## Parameters

`D3DKMT_CHECKMONITORPOWERSTATE`

TBD


## Return Value

<b>D3DKMTCheckMonitorPowerState</b> returns one of the following values:

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
The power state of the monitor was successfully verified.

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
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_checkmonitorpowerstate.md">D3DKMT_CHECKMONITORPOWERSTATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_CHECKMONITORPOWERSTATE callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>