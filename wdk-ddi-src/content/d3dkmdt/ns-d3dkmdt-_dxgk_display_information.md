---
UID: NS:d3dkmdt._DXGK_DISPLAY_INFORMATION
title: "_DXGK_DISPLAY_INFORMATION"
author: windows-driver-content
description: Contains the display information that is passed between the operating system and the display miniport driver when the driver is started or stopped in response to a Plug and Play (PnP) event.
old-location: display\dxgk_display_information.htm
old-project: display
ms.assetid: e6902724-a81b-4a06-8089-a8e98392dc78
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGK_DISPLAY_INFORMATION, DXGK_DISPLAY_INFORMATION, DXGK_DISPLAY_INFORMATION structure [Display Devices], PDXGK_DISPLAY_INFORMATION, PDXGK_DISPLAY_INFORMATION structure pointer [Display Devices], _DXGK_DISPLAY_INFORMATION, d3dkmdt/DXGK_DISPLAY_INFORMATION, d3dkmdt/PDXGK_DISPLAY_INFORMATION, display.dxgk_display_information"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmdt.h
api_name:
-	DXGK_DISPLAY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: DXGK_DISPLAY_INFORMATION, *PDXGK_DISPLAY_INFORMATION
---

# _DXGK_DISPLAY_INFORMATION structure
Contains the display information that is passed between the operating system and the display miniport driver when the driver is started or stopped in response to a Plug and Play (PnP) event.

## Syntax
```
typedef struct _DXGK_DISPLAY_INFORMATION {
  UINT                           Width;
  UINT                           Height;
  UINT                           Pitch;
  D3DDDIFORMAT                   ColorFormat;
  PHYSICAL_ADDRESS               PhysicAddress;
  D3DDDI_VIDEO_PRESENT_TARGET_ID TargetId;
  ULONG                          AcpiId;
} *PDXGK_DISPLAY_INFORMATION, DXGK_DISPLAY_INFORMATION;
```

## Members


`Width`

A UINT value that specifies the width of the current display mode in units of pixels.

`Height`

A UINT value that specifies the height of the current display mode  in units of pixels.

`Pitch`

A UINT value that specifies the total number of bytes contained in one screen line.

`ColorFormat`

A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a> that indicates the pixel color format of the current display mode. The driver does not have to support all color formats in the <b>D3DDDIFORMAT</b> structure. For more information on formats that must be supported, see <a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a> and <a href="https://msdn.microsoft.com/6AF170BF-C422-4340-8935-31A4D4F3EFA5">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>.

`PhysicAddress`

The physical start address of the frame buffer for the current display mode.

`TargetId`

An integer value that specifies the identifier of the video present target on the display adapter that the display device is connected to.

`AcpiId`

A ULONG value that specifies the ACPI identifier of the video present target specified by the <b>TargetId</b> member.

<div class="alert"><b>Note</b>  If the video present target is not an ACPI device, this member must be set to zero.</div>
<div> </div>

## Remarks
For more information on the use of the members of <b>DXGK_DISPLAY_INFORMATION</b>, see <a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a> and <a href="https://msdn.microsoft.com/6AF170BF-C422-4340-8935-31A4D4F3EFA5">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a>



<a href="https://msdn.microsoft.com/6AF170BF-C422-4340-8935-31A4D4F3EFA5">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>