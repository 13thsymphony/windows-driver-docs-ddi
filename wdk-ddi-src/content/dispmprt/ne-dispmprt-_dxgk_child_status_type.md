---
UID: NE:dispmprt._DXGK_CHILD_STATUS_TYPE
title: "_DXGK_CHILD_STATUS_TYPE"
author: windows-driver-content
description: The DXGK_CHILD_STATUS_TYPE enumeration indicates the type of status being requested or reported for a child device of the display adapter.
old-location: display\dxgk_child_status_type.htm
old-project: display
ms.assetid: 5fa4b7e2-8215-49d8-9d70-b45c972b39b4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDXGK_CHILD_STATUS_TYPE, DXGK_CHILD_STATUS_TYPE, DXGK_CHILD_STATUS_TYPE enumeration [Display Devices], DmEnums_684c935e-6fd5-4743-a196-d6674b8f2e56.xml, PDXGK_CHILD_STATUS_TYPE, PDXGK_CHILD_STATUS_TYPE enumeration pointer [Display Devices], StatusConnection, StatusMiracast, StatusRotation, StatusUninitialized, _DXGK_CHILD_STATUS_TYPE, display.dxgk_child_status_type, dispmprt/DXGK_CHILD_STATUS_TYPE, dispmprt/PDXGK_CHILD_STATUS_TYPE, dispmprt/StatusConnection, dispmprt/StatusMiracast, dispmprt/StatusRotation, dispmprt/StatusUninitialized"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
-	dispmprt.h
api_name:
-	DXGK_CHILD_STATUS_TYPE
product: Windows
targetos: Windows
req.typenames: DXGK_CHILD_STATUS_TYPE, *PDXGK_CHILD_STATUS_TYPE
---

# _DXGK_CHILD_STATUS_TYPE Enumeration
The DXGK_CHILD_STATUS_TYPE enumeration indicates the type of status being requested or reported for a child device of the display adapter.

## Syntax
````
typedef enum _DXGK_CHILD_STATUS_TYPE { 
  StatusUninitialized,
  StatusConnection,
  StatusRotation,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  StatusMiracast

#endif } DXGK_CHILD_STATUS_TYPE, *PDXGK_CHILD_STATUS_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>StatusConnection</td>
                    <td>Indicates that the request or report pertains to whether the child device has a monitor (or other display device) connected to it.</td>
                </tr>
            
                <tr>
                    <td>StatusMiracastConnection</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>StatusRotation</td>
                    <td>Indicates that the request or report pertains to the rotation angle of the monitor (or other display device) that is connected to the child device.</td>
                </tr>
            
                <tr>
                    <td>StatusUninitialized</td>
                    <td>Indicates that a variable of type DXGK_CHILD_STATUS_TYPE has not yet been assigned a meaningful value.</td>
                </tr>
</table>

## Remarks

The <b>Type</b> member of a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_status.md">DXGK_CHILD_STATUS</a> structure is a member of the <b>DXGK_CHILD_STATUS_TYPE</b> enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_status.md">DxgkDdiQueryChildStatus</a>



<a href="..\dispmprt\nc-dispmprt-dxgkcb_indicate_child_status.md">DxgkCbIndicateChildStatus</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_CHILD_STATUS_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>