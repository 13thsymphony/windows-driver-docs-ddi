---
UID: NE:d3dkmddi._DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
title: "_DXGK_RECOMMENDFUNCTIONALVIDPN_REASON"
author: windows-driver-content
description: The DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration indicates the reason for calling the display miniport driver's DxgkDdiRecommendFunctionalVidPn function.
old-location: display\dxgk_recommendfunctionalvidpn_reason.htm
old-project: display
ms.assetid: 75dda423-8d5a-4b11-a187-d6703601a366
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_RFVR_FIRMWARE, _DXGK_RECOMMENDFUNCTIONALVIDPN_REASON, DXGK_RFVR_USERMODE, d3dkmddi/DXGK_RFVR_USERMODE, d3dkmddi/DXGK_RFVR_UNINITIALIZED, DXGK_RECOMMENDFUNCTIONALVIDPN_REASON, DXGK_RFVR_UNINITIALIZED, DmEnums_bb915c39-0ecd-4b15-8030-6a144173dc90.xml, d3dkmddi/DXGK_RECOMMENDFUNCTIONALVIDPN_REASON, display.dxgk_recommendfunctionalvidpn_reason, d3dkmddi/DXGK_RFVR_HOTKEY, DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration [Display Devices], DXGK_RFVR_FIRMWARE, DXGK_RFVR_HOTKEY
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
product: Windows
targetos: Windows
req.typenames: DXGK_RECOMMENDFUNCTIONALVIDPN_REASON
---

# _DXGK_RECOMMENDFUNCTIONALVIDPN_REASON Enumeration
The DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration indicates the reason for calling the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a> function.

## Syntax
````
typedef enum _DXGK_RECOMMENDFUNCTIONALVIDPN_REASON { 
  DXGK_RFVR_UNINITIALIZED  = 0,
  DXGK_RFVR_HOTKEY         = 1,
  DXGK_RFVR_USERMODE       = 2,
  DXGK_RFVR_FIRMWARE       = 3
} DXGK_RECOMMENDFUNCTIONALVIDPN_REASON;
````

## Constants

<table>
            
                <tr>
                    <td>DXGK_RFVR_FIRMWARE</td>
                    <td>Value indicating that the OS is requesting the driver to describe a functional VidPn which reflects the display topology and timings which are currently set, as inherited from firmware during boot or resume from hibernation.</td>
                </tr>
            
                <tr>
                    <td>DXGK_RFVR_HOTKEY</td>
                    <td>Indicates that the VidPN manager is calling <i>DxgkDdiRecommendFunctionalVidPn</i> because the user pressed a hot key to request a change in the way the desktop is displayed on a collection of monitors (or other display devices).</td>
                </tr>
            
                <tr>
                    <td>DXGK_RFVR_UNINITIALIZED</td>
                    <td>Indicates that a variable of type DXGK_RECOMMENDFUNCTIONALVIDPN_REASON has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>DXGK_RFVR_USERMODE</td>
                    <td>Indicates that a user-mode application initiated a call to <i>DxgkDdiRecommendFunctionalVidPn</i>.</td>
                </tr>
</table>

## Remarks

The <b>RequestReason</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_recommendfunctionalvidpn.md">DXGKARG_RECOMMENDFUNCTIONALVIDPN</a> structure is a DXGK_RECOMMENDFUNCTIONALVIDPN_REASON value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>