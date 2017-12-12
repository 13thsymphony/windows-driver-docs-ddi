---
UID: NS.DXVA._DXVA_PROCAMPCONTROLQUERYRANGE
title: _DXVA_ProcAmpControlQueryRange
author: windows-driver-content
description: The DXVA_ProcAmpControlQueryRange structure contains the minimum, maximum, step size, and default value for each ProcAmp property.
old-location: display\dxva_procampcontrolqueryrange.htm
old-project: display
ms.assetid: 934b69cd-f54d-4706-bcb6-8d9e25ea3367
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVA_ProcAmpControlQueryRange, *LPDXVA_ProcAmpControlQueryRange, DXVA_ProcAmpControlQueryRange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: DirectX 9.0 and later versions only.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_ProcAmpControlQueryRange
req.alt-loc: dxva.h
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

# _DXVA_ProcAmpControlQueryRange structure



## -description
The DXVA_ProcAmpControlQueryRange structure contains the minimum, maximum, step size, and default value for each ProcAmp property.



## -syntax

````
typedef struct _DXVA_ProcAmpControlQueryRange {
  DWORD                   Size;
  DXVA_ProcAmpControlProp ProcAmpControlProp;
  DXVA_VideoDesc          VideoDesc;
} DXVA_ProcAmpControlQueryRange, *LPDXVA_ProcAmpControlQueryRange;
````


## -struct-fields

### -field Size

Specifies the size of this structure in bytes.


### -field ProcAmpControlProp

Specifies a <a href="display.dxva_procampcontrolprop">DXVA_ProcAmpControlProp</a> structure that indicates the supported ProcAmp control properties.


### -field VideoDesc

Specifies a <a href="display.dxva_videodesc">DXVA_VideoDesc</a> structure that provides the driver with a description of the video that the ProcAmp adjustment is going to be applied to. Drivers may adjust their ProcAmp feature support for particular video streams.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
DirectX 9.0 and later versions only.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxva_videodesc">DXVA_VideoDesc</a>
</dt>
<dt>
<a href="display.dxva_procampcontrolprop">DXVA_ProcAmpControlProp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_ProcAmpControlQueryRange structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

