---
UID : NE:d3dumddi.D3DDDI_CHECK_DIRECT_FLIP_FLAGS
title : D3DDDI_CHECK_DIRECT_FLIP_FLAGS
author : windows-driver-content
description : Used by the CheckDirectFlipFlags parameter of the CheckDirectFlipSupport function to specify seamless flipping of video memory.
old-location : display\d3dddi_check_direct_flip_flags.htm
old-project : display
ms.assetid : 72b49af8-4d98-4fc0-ab40-72f1e19eef96
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DDDI_CHECK_DIRECT_FLIP_FLAGS, D3DDDI_CHECK_DIRECT_FLIP_FLAGS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dumddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DDDI_CHECK_DIRECT_FLIP_FLAGS
req.alt-loc : D3dumddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : D3DDDI_CHECK_DIRECT_FLIP_FLAGS
---

# D3DDDI_CHECK_DIRECT_FLIP_FLAGS Enumeration
Used by the <i>CheckDirectFlipFlags</i> parameter of the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_checkdirectflipsupport.md">CheckDirectFlipSupport</a> function to specify seamless flipping of video memory.

## Syntax
````
typedef enum D3DDDI_CHECK_DIRECT_FLIP_FLAGS { 
  D3DDDI_CHECKDIRECTFLIP_IMMEDIATE  = 0x00000001
} D3DDDI_CHECK_DIRECT_FLIP_FLAGS;
````

## Constants

<table>

<tr>
<td>D3DDDI_CHECKDIRECTFLIP_IMMEDIATE</td>
<td>Seamless flipping should occur immediately and does not have to be synchronized with a VSync interrupt.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h |

## See Also

<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_checkdirectflipsupport.md">CheckDirectFlipSupport</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi-d3dddi_check_direct_flip_flags.md">D3DDDI_CHECK_DIRECT_FLIP_FLAGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_CHECK_DIRECT_FLIP_FLAGS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>