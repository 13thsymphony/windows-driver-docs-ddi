---
UID: NS.d3dumddi._DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
title: DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure describes data that specifies the target rectangle of the output.
old-location: display\dxvahdddi_blt_state_target_rect_data.htm
old-project: display
ms.assetid: d6b76b6b-59d9-441f-846e-fe89d26f631d
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA, DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
req.alt-loc: d3dumddi.h
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
req.iface: 
---

# DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure



## -description
<p>The DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure describes data that specifies the target rectangle of the output. </p>


## -syntax

````
typedef struct _DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA {
  BOOL Enable;
  RECT TargetRect;
} DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA;
````


## -struct-fields
<dl>

### -field <b>Enable</b>

<dd>
<p>[in] A Boolean value that specifies whether the driver should use the <b>TargetRect</b> member or the entire output surface as the target. The default value is <b>FALSE</b>, which indicates that the entire output surface is the target. </p>
</dd>

### -field <b>TargetRect</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the target rectangle in the coordinates of the output surface. This member is relevant only when the <b>Enable</b> member is set to <b>TRUE</b>. The default value is (0,0,0,0).</p>
</dd>
</dl>

## -remarks
<p>If the <b>Enable</b> member is set to <b>TRUE</b> and the target rectangle that the <b>TargetRect</b> member specifies is not within the output surface, the intersection of the target rectangle and the output surface is used as the target rectangle. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA is supported beginning with the Windows 7 operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
