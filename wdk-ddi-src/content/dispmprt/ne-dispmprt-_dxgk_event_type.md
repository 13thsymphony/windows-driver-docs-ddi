---
UID: NE:dispmprt._DXGK_EVENT_TYPE
title: "_DXGK_EVENT_TYPE"
author: windows-driver-content
description: The DXGK_EVENT_TYPE enumeration indicates the event type in a call to the display miniport driver's DxgkDdiNotifyAcpiEvent function.
old-location: display\dxgk_event_type.htm
old-project: display
ms.assetid: df28ae8f-01f7-42c5-99df-2a3fc7401173
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dispmprt/DXGK_EVENT_TYPE, display.dxgk_event_type, dispmprt/PDXGK_EVENT_TYPE, _DXGK_EVENT_TYPE, PDXGK_EVENT_TYPE enumeration pointer [Display Devices], *PDXGK_EVENT_TYPE, PDXGK_EVENT_TYPE, DXGK_EVENT_TYPE enumeration [Display Devices], DxgkPowerStateEvent, dispmprt/DxgkDockingEvent, DmEnums_94bee105-be3f-4268-982e-be8581bb9bc0.xml, DxgkUndefinedEvent, DxgkDockingEvent, dispmprt/DxgkAcpiEvent, dispmprt/DxgkUndefinedEvent, IN_DXGK_EVENT_TYPE, dispmprt/DxgkPowerStateEvent, DXGK_EVENT_TYPE, DxgkAcpiEvent
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dispmprt.h
apiname:
-	DXGK_EVENT_TYPE
product: Windows
targetos: Windows
req.typenames: DXGK_EVENT_TYPE, *PDXGK_EVENT_TYPE
---

# _DXGK_EVENT_TYPE Enumeration
The DXGK_EVENT_TYPE enumeration indicates the event type in a call to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_acpi_event.md">DxgkDdiNotifyAcpiEvent</a> function.

## Syntax
````
typedef enum _DXGK_EVENT_TYPE { 
  DxgkUndefinedEvent   = 0,
  DxgkAcpiEvent        = 1,
  DxgkPowerStateEvent  = 2,
  DxgkDockingEvent     = 3
} DXGK_EVENT_TYPE, *PDXGK_EVENT_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>DxgkAcpiEvent</td>
                    <td>Indicates that the event is an ACPI event.</td>
                </tr>
            
                <tr>
                    <td>DxgkChainedAcpiEvent</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>DxgkDockingEvent</td>
                    <td>Indicates that the event is a docking event.</td>
                </tr>
            
                <tr>
                    <td>DxgkPowerStateEvent</td>
                    <td>Indicates that the event is a power state event.</td>
                </tr>
            
                <tr>
                    <td>DxgkUndefinedEvent</td>
                    <td>Indicates that a variable of type DXGK_EVENT_TYPE has not yet been assigned a meaningful value.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dispmprt.h (include Dispmprt.h) |

    ## See Also

        <a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_acpi_event.md">DxgkDdiNotifyAcpiEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_EVENT_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>