---
UID : NS:d3dkmthk._D3DKMT_FLIPOVERLAY
title : "_D3DKMT_FLIPOVERLAY"
author : windows-driver-content
description : The D3DKMT_FLIPOVERLAY structure describes a new allocation to display for the overlay.
old-location : display\d3dkmt_flipoverlay.htm
old-project : display
ms.assetid : 7e224009-dccb-41e5-99e8-01f1479aa79f
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DKMT_FLIPOVERLAY structure [Display Devices], d3dkmthk/D3DKMT_FLIPOVERLAY, OpenGL_Structs_a7694ad8-b12e-41ad-b7e3-159d26fe2f41.xml, D3DKMT_FLIPOVERLAY, display.d3dkmt_flipoverlay, _D3DKMT_FLIPOVERLAY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMT_FLIPOVERLAY
---

# _D3DKMT_FLIPOVERLAY structure
The D3DKMT_FLIPOVERLAY structure describes a new allocation to display for the overlay.

## Syntax
````
typedef struct _D3DKMT_FLIPOVERLAY {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hOverlay;
  D3DKMT_HANDLE hSource;
  VOID          *pPrivateDriverData;
  UINT          PrivateDriverDataSize;
} D3DKMT_FLIPOVERLAY;
````

## Members


`hDevice`

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device that the overlay is associated with.

`hOverlay`

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the create-overlay function and that identifies the kernel-mode overlay object to be flipped.

`hSource`

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the source allocation to be displayed.

`pPrivateDriverData`

[in] A pointer to a block of private data, which is passed from the OpenGL ICD to the display miniport driver.

`PrivateDriverDataSize`

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtflipoverlay.md">D3DKMTFlipOverlay</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_FLIPOVERLAY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>