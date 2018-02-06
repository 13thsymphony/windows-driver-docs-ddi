---
UID: NE:d3d10umddi.D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS
title: D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS
author: windows-driver-content
description: Used by the CheckDirectFlipFlags parameter of the CheckDirectFlipSupport(D3D11_1) function to specify seamless flipping of video memory.
old-location: display\d3d11_1_ddi_check_direct_flip_flags.htm
old-project: display
ms.assetid: beead760-8f93-48da-b2fc-2f8a0031019c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS enumeration [Display Devices], display.d3d11_1_ddi_check_direct_flip_flags, D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE, d3d10umddi/D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE, D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS, d3d10umddi/D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS
product: Windows
targetos: Windows
req.typenames: D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS
---

# D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS Enumeration
Used by the <i>CheckDirectFlipFlags</i> parameter of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_checkdirectflipsupport.md">CheckDirectFlipSupport(D3D11_1)</a> function to specify seamless flipping of video memory.

## Syntax
````
typedef enum D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS { 
  D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE  = 0x00000001
} D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE</td>
                    <td>Seamless flipping should occur immediately and does not have to be synchronized with a VSync interrupt.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

    ## See Also

        <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_checkdirectflipsupport.md">CheckDirectFlipSupport(D3D11_1)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>