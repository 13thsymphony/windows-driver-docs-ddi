---
UID: NE.d3dkmdt._D3DKMDT_MONITOR_CONNECTIVITY_CHECKS
title: _D3DKMDT_MONITOR_CONNECTIVITY_CHECKS
author: windows-driver-content
description: The D3DKMDT_MONITOR_CONNECTIVITY_CHECKS enumerated type indicates whether the DxgkDdiCommitVidPn function should verify that certain video outputs have connected monitors.
old-location: display\d3dkmdt_monitor_connectivity_checks.htm
old-project: display
ms.assetid: 8a32fef1-e404-478d-8b99-064ed456e37c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMDT_MONITOR_CONNECTIVITY_CHECKS, D3DKMDT_MONITOR_CONNECTIVITY_CHECKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_MONITOR_CONNECTIVITY_CHECKS
req.alt-loc: d3dkmdt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _D3DKMDT_MONITOR_CONNECTIVITY_CHECKS enumeration



## -description
The D3DKMDT_MONITOR_CONNECTIVITY_CHECKS enumerated type indicates whether the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a> function should verify that certain video outputs have connected monitors.



## -syntax

````
typedef enum _D3DKMDT_MONITOR_CONNECTIVITY_CHECKS { 
  D3DKMDT_MCC_UNINITIALIZED  = 0,
  D3DKMDT_MCC_IGNORE         = 1,
  D3DKMDT_MCC_ENFORCE        = 2
} D3DKMDT_MONITOR_CONNECTIVITY_CHECKS;
````


## -enum-fields

### -field D3DKMDT_MCC_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MONITOR_CONNECTIVITY_CHECKS has not yet been assigned a meaningful value.


### -field D3DKMDT_MCC_IGNORE

Indicates that <b>DxgkDdiCommitVidPn</b> does not need to verify that monitors are connected.


### -field D3DKMDT_MCC_ENFORCE

Indicates that <b>DxgkDdiCommitVidPn</b> must verify that monitors are connected.


## -remarks
The <b>MonitorConnectivityChecks</b> member of the <a href="display.dxgkarg_commitvidpn">DXGKARG_COMMITVIDPN</a> structure is a D3DKMDT_MONITOR_CONNECTIVITY_CHECKS value.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_MONITOR_CONNECTIVITY_CHECKS enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

