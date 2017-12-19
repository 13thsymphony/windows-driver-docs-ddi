---
UID: NS.D3DKMDDI._DXGK_GPUENGINETOPOLOGY
title: _DXGK_GPUENGINETOPOLOGY
author: windows-driver-content
description: The DXGK_GPUENGINETOPOLOGY structure describes the graphics processing unit (GPU)-engine topology that a driver can support.
old-location: display\dxgk_gpuenginetopology.htm
old-project: display
ms.assetid: 8ed224eb-c1f6-4793-ae32-36f96d3af9ab
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_GPUENGINETOPOLOGY, DXGK_GPUENGINETOPOLOGY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_GPUENGINETOPOLOGY
req.alt-loc: d3dkmddi.h
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

# _DXGK_GPUENGINETOPOLOGY structure



## -description
The DXGK_GPUENGINETOPOLOGY structure describes the graphics processing unit (GPU)-engine topology that a driver can support.



## -syntax

````
typedef struct _DXGK_GPUENGINETOPOLOGY {
  UINT NbAsymetricProcessingNodes;
  UINT Reserved[DXGK_MAX_ASYMETRICAL_PROCESSING_NODES];
} DXGK_GPUENGINETOPOLOGY;
````


## -struct-fields

### -field NbAsymetricProcessingNodes

[out] The number of parallel engines that the GPU supports. If the driver does not set the <b>MultiEngineAware</b> bit-field flag in the <b>SchedulingCaps</b> member of the <a href="display.dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure, the Microsoft DirectX graphics kernel subsystem ignores the setting of <b>NbAsymetricProcessingNodes</b>.


### -field Reserved

[out] An array of 32-bit values that are reserved for future use. The <b>DXGK_MAX_ASYMETRICAL_PROCESSING_NODES</b> constant, which is defined as 64, indicates the maximum number of asymmetrical processing nodes that the driver can signal.


## -remarks


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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgk_drivercaps">DXGK_DRIVERCAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_GPUENGINETOPOLOGY structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

