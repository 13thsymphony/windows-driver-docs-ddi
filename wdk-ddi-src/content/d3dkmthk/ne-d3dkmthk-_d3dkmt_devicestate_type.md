---
UID: NE:d3dkmthk._D3DKMT_DEVICESTATE_TYPE
title: "_D3DKMT_DEVICESTATE_TYPE"
author: windows-driver-content
description: The D3DKMT_DEVICESTATE_TYPE enumeration type contains values that indicate the status of a device.
old-location: display\d3dkmt_devicestate_type.htm
old-project: display
ms.assetid: 84570bac-63f1-4e34-919f-c150f9f0810e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_DEVICESTATE_PRESENT_DWM, display.d3dkmt_devicestate_type, d3dkmthk/D3DKMT_DEVICESTATE_EXECUTION, d3dkmthk/D3DKMT_DEVICESTATE_PAGE_FAULT, D3DKMT_DEVICESTATE_PAGE_FAULT, D3DKMT_DEVICESTATE_EXECUTION, OpenGL_Structs_7446b76d-102c-4d61-bf39-ce1ca17ea036.xml, d3dkmthk/D3DKMT_DEVICESTATE_PRESENT_DWM, d3dkmthk/, D3DKMT_DEVICESTATE_TYPE, _D3DKMT_DEVICESTATE_TYPE, D3DKMT_DEVICESTATE_TYPE enumeration [Display Devices], d3dkmthk/D3DKMT_DEVICESTATE_RESET, d3dkmthk/D3DKMT_DEVICESTATE_TYPE, D3DKMT_DEVICESTATE_PRESENT, d3dkmthk/D3DKMT_DEVICESTATE_PRESENT, D3DKMT_DEVICESTATE_RESET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3DKMT_DEVICESTATE_TYPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DEVICESTATE_TYPE
---

# _D3DKMT_DEVICESTATE_TYPE Enumeration
The D3DKMT_DEVICESTATE_TYPE enumeration type contains values that indicate the status of a device.

## Syntax
````
typedef enum _D3DKMT_DEVICESTATE_TYPE { 
  D3DKMT_DEVICESTATE_EXECUTION    = 1,
  D3DKMT_DEVICESTATE_PRESENT      = 2,
  D3DKMT_DEVICESTATE_RESET        = 3,
  D3DKMT_DEVICESTATE_PRESENT_DWM  = 4,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  D3DKMT_DEVICESTATE_PAGE_FAULT   = 5,
#endif 
  
} D3DKMT_DEVICESTATE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>D3DKMT_DEVICESTATE_EXECUTION</td>
                    <td>The device execution state is retrieved.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_DEVICESTATE_PAGE_FAULT</td>
                    <td>The device page fault state is retrieved.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_DEVICESTATE_PRESENT</td>
                    <td>The device present state is retrieved.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_DEVICESTATE_PRESENT_DWM</td>
                    <td>The device present desktop window manager state is retrieved.</td>
                </tr>
            
                <tr>
                    <td>D3DKMT_DEVICESTATE_PRESENT_QUEUE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DKMT_DEVICESTATE_RESET</td>
                    <td>The device reset state is retrieved.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

    ## See Also

        <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdevicestate.md">D3DKMT_GETDEVICESTATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DEVICESTATE_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>