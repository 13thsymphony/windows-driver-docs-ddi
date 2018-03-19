---
UID: NE:d3dkmddi._DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
title: "_DXGK_ACTIVE_VIDPN_INVALIDATION_REASON"
author: windows-driver-content
description: The DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration is used to indicate the reason why an active VidPN is invalidated and a new VidPN is requested.
old-location: display\dxgk_active_vidpn_invalidation_reason.htm
old-project: display
ms.assetid: e1f33307-1bb0-4cdd-aa47-954f6e551582
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_ACTIVE_VIDPN_INVALIDATION_REASON, DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration [Display Devices], DXGK_AVIR_HOTKEY, DXGK_AVIR_UNINITIALIZED, DXGK_AVIR_USERMODE, DmEnums_9a263431-3cae-4e33-a2f0-310ec88c1343.xml, _DXGK_ACTIVE_VIDPN_INVALIDATION_REASON, d3dkmddi/DXGK_ACTIVE_VIDPN_INVALIDATION_REASON, d3dkmddi/DXGK_AVIR_HOTKEY, d3dkmddi/DXGK_AVIR_UNINITIALIZED, d3dkmddi/DXGK_AVIR_USERMODE, display.dxgk_active_vidpn_invalidation_reason
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
product: Windows
targetos: Windows
req.typenames: DXGK_ACTIVE_VIDPN_INVALIDATION_REASON
---

# _DXGK_ACTIVE_VIDPN_INVALIDATION_REASON Enumeration
The DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration is used to indicate the reason why an active VidPN is invalidated and a new VidPN is requested.

## Syntax
````
typedef enum _DXGK_ACTIVE_VIDPN_INVALIDATION_REASON { 
  DXGK_AVIR_UNINITIALIZED  = DXGK_RFVR_UNINITIALIZED,
  DXGK_AVIR_HOTKEY         = DXGK_RFVR_HOTKEY,
  DXGK_AVIR_USERMODE       = DXGK_RFVR_USERMODE
} DXGK_ACTIVE_VIDPN_INVALIDATION_REASON;
````

## Constants

<table>
            
                <tr>
                    <td>DXGK_AVIR_UNINITIALIZED</td>
                    <td>Indicates that a variable of type DXGK_ACTIVE_VIDPN_INVALIDATION_REASON has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>DXGK_AVIR_HOTKEY</td>
                    <td>Indicates that the user pressed a keyboard shortcut to change the set of monitors (or other display devices) being used to display the desktop.</td>
                </tr>
            
                <tr>
                    <td>DXGK_AVIR_USERMODE</td>
                    <td>Indicates that a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtinvalidateactivevidpn.md">D3DKMTInvalidateActiveVidPn</a> function has been made in user mode.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtinvalidateactivevidpn.md">D3DKMTInvalidateActiveVidPN</a>