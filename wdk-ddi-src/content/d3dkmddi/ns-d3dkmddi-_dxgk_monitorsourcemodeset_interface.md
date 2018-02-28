---
UID: NS:d3dkmddi._DXGK_MONITORSOURCEMODESET_INTERFACE
title: "_DXGK_MONITORSOURCEMODESET_INTERFACE"
author: windows-driver-content
description: The DXGK_MONITORSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the Monitor Source Mode Set interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitorsourcemodeset_interface.htm
old-project: display
ms.assetid: ceab36a0-3be1-41d8-82c0-8393f93e5f42
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGK_MONITORSOURCEMODESET_INTERFACE, DXGK_MONITORSOURCEMODESET_INTERFACE structure [Display Devices], DmStructs_c4c7e928-09db-424f-8ac7-7efffc71d06e.xml, _DXGK_MONITORSOURCEMODESET_INTERFACE, d3dkmddi/DXGK_MONITORSOURCEMODESET_INTERFACE, display.dxgk_monitorsourcemodeset_interface
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
-	DXGK_MONITORSOURCEMODESET_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_MONITORSOURCEMODESET_INTERFACE
---

# _DXGK_MONITORSOURCEMODESET_INTERFACE structure
The DXGK_MONITORSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568435">Monitor Source Mode Set interface</a>, which is implemented by the video present network (VidPN) manager.

## Syntax
````
typedef struct _DXGK_MONITORSOURCEMODESET_INTERFACE {
  DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES              pfnGetNumModes;
  DXGKDDI_MONITORSOURCEMODESET_ACQUIREPREFERREDMODEINFO pfnAcquirePreferredModeInfo;
  DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO     pfnAcquireFirstModeInfo;
  DXGKDDI_MONITORSOURCEMODESET_ACQUIRENEXTMODEINFO      pfnAcquireNextModeInfo;
  DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO        pfnCreateNewModeInfo;
  DXGKDDI_MONITORSOURCEMODESET_ADDMODE                  pfnAddMode;
  DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO          pfnReleaseModeInfo;
} DXGK_MONITORSOURCEMODESET_INTERFACE;
````

## Members


`pfnAcquireFirstModeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a> function.

`pfnAcquireNextModeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirenextmodeinfo.md">pfnAcquireNextModeInfo</a> function.

`pfnAcquirePreferredModeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirepreferredmodeinfo.md">pfnAcquirePreferredModeInfo</a> function.

`pfnAddMode`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_addmode.md">pfnAddMode</a> function.

`pfnCreateNewModeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a> function.

`pfnGetNumModes`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_getnummodes.md">pfnGetNumModes</a> function.

`pfnReleaseModeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a> function.

## Remarks
The display miniport driver calls the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a> to obtain a handle to a monitor source mode set object and a pointer to a DXGK_MONITORSOURCEMODESET_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the monitor source mode set object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md">pfnAcquireMonitorSourceModeSet</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpntargetmodeset_interface.md">DXGK_VIDPNTARGETMODESET_INTERFACE</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface.md">DXGK_VIDPNSOURCEMODESET_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MONITORSOURCEMODESET_INTERFACE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>