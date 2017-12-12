---
UID: NE.d3dkmddi._DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
title: _DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
author: windows-driver-content
description: The DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration indicates the reason for calling the display miniport driver's DxgkDdiRecommendFunctionalVidPn function.
old-location: display\dxgk_recommendfunctionalvidpn_reason.htm
old-project: display
ms.assetid: 75dda423-8d5a-4b11-a187-d6703601a366
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_RECOMMENDFUNCTIONALVIDPN_REASON, DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
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

# _DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration



## -description
The DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration indicates the reason for calling the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a> function.



## -syntax

````
typedef enum _DXGK_RECOMMENDFUNCTIONALVIDPN_REASON { 
  DXGK_RFVR_UNINITIALIZED  = 0,
  DXGK_RFVR_HOTKEY         = 1,
  DXGK_RFVR_USERMODE       = 2,
  DXGK_RFVR_FIRMWARE       = 3
} DXGK_RECOMMENDFUNCTIONALVIDPN_REASON;
````


## -enum-fields

### -field DXGK_RFVR_UNINITIALIZED

Indicates that a variable of type DXGK_RECOMMENDFUNCTIONALVIDPN_REASON has not yet been assigned a meaningful value.


### -field DXGK_RFVR_HOTKEY

Indicates that the VidPN manager is calling <i>DxgkDdiRecommendFunctionalVidPn</i> because the user pressed a hot key to request a change in the way the desktop is displayed on a collection of monitors (or other display devices).


### -field DXGK_RFVR_USERMODE

Indicates that a user-mode application initiated a call to <i>DxgkDdiRecommendFunctionalVidPn</i>.


### -field DXGK_RFVR_FIRMWARE

Value indicating that the OS is requesting the driver to describe a functional VidPn which reflects the display topology and timings which are currently set, as inherited from firmware during boot or resume from hibernation.


## -remarks
The <b>RequestReason</b> member of the <a href="display.dxgkarg_recommendfunctionalvidpn">DXGKARG_RECOMMENDFUNCTIONALVIDPN</a> structure is a DXGK_RECOMMENDFUNCTIONALVIDPN_REASON value.


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
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

