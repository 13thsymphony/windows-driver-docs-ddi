---
UID: NS:d3dkmthk._D3DKMT_UPDATEOVERLAY
title: "_D3DKMT_UPDATEOVERLAY"
author: windows-driver-content
description: The D3DKMT_UPDATEOVERLAY structure describes parameters for modifying an overlay.
old-location: display\d3dkmt_updateoverlay.htm
old-project: display
ms.assetid: 4e7d4d09-067b-4658-ab2a-319dc9e6d8db
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmt_updateoverlay, _D3DKMT_UPDATEOVERLAY, d3dkmthk/D3DKMT_UPDATEOVERLAY, OpenGL_Structs_763acbbf-27ad-4d91-903f-7200b7d7e0cf.xml, D3DKMT_UPDATEOVERLAY structure [Display Devices], D3DKMT_UPDATEOVERLAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_UPDATEOVERLAY
product: Windows
targetos: Windows
req.typenames: D3DKMT_UPDATEOVERLAY
---

# _D3DKMT_UPDATEOVERLAY structure
The D3DKMT_UPDATEOVERLAY structure describes parameters for modifying an overlay.

## Syntax
````
typedef struct _D3DKMT_UPDATEOVERLAY {
  D3DKMT_HANDLE            hDevice;
  D3DKMT_HANDLE            hOverlay;
  D3DDDI_KERNELOVERLAYINFO OverlayInfo;
} D3DKMT_UPDATEOVERLAY;
````

## Members


`hDevice`

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device that the overlay is associated with.

`hOverlay`

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the create-overlay function and that identifies the kernel-mode overlay object to modify.

`OverlayInfo`

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_kerneloverlayinfo.md">D3DDDI_KERNELOVERLAYINFO</a> structure that describes modification information for the kernel-mode overlay object.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtupdateoverlay.md">D3DKMTUpdateOverlay</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_kerneloverlayinfo.md">D3DDDI_KERNELOVERLAYINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_UPDATEOVERLAY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>