---
UID: NS:d3dkmthk._D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
title: "_D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME"
author: windows-driver-content
description: The D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure describes the mapping of the given name of a GDI device to a graphics adapter handle and monitor output.
old-location: display\d3dkmt_openadapterfromgdidisplayname.htm
old-project: display
ms.assetid: 8b166fbb-f6fa-4d90-9b32-40ce213cbd71
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME, D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure [Display Devices], OpenGL_Structs_a6a0807b-454b-48a4-91d1-26d62e592280.xml, _D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME, d3dkmthk/D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME, display.d3dkmt_openadapterfromgdidisplayname
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
---

# _D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure
The D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure describes the mapping of the given name of a GDI device to a graphics adapter handle and monitor output.

## Syntax
````
typedef struct _D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME {
  WCHAR                          DeviceName[32];
  D3DKMT_HANDLE                  hAdapter;
  LUID                           AdapterLuid;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME;
````

## Members


`AdapterLuid`

[out] The locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) of the graphics adapter for the GDI device that <b>DeviceName</b> specifies. The LUID is returned from the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromgdidisplayname.md">D3DKMTOpenAdapterFromGdiDisplayName</a> call.

`DeviceName`

[in] A Unicode string that contains the name of the GDI device from which to open an adapter instance.

`hAdapter`

[out] A handle to the graphics adapter for the GDI device that <b>DeviceName</b> specifies. The adapter handle is returned from the call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromgdidisplayname.md">D3DKMTOpenAdapterFromGdiDisplayName</a> function.

`VidPnSourceId`

[out] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the GDI device that <b>DeviceName</b> specifies. The identification number is returned from the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromgdidisplayname.md">D3DKMTOpenAdapterFromGdiDisplayName</a> call.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromgdidisplayname.md">D3DKMTOpenAdapterFromGdiDisplayName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>