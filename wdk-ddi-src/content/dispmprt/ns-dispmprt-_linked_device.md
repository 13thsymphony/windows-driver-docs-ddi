---
UID: NS:dispmprt._LINKED_DEVICE
title: "_LINKED_DEVICE"
author: windows-driver-content
description: The LINKED_DEVICE structure holds information that describes a linked display adapter configuration.
old-location: display\linked_device.htm
old-project: display
ms.assetid: 65289123-46b8-4a4b-985a-8087f4afd250
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PLINKED_DEVICE, DmStructs_3491af70-72fe-471c-b0f1-c00d6bffb242.xml, LINKED_DEVICE, LINKED_DEVICE structure [Display Devices], PLINKED_DEVICE, PLINKED_DEVICE structure pointer [Display Devices], _LINKED_DEVICE, display.linked_device, dispmprt/LINKED_DEVICE, dispmprt/PLINKED_DEVICE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	LINKED_DEVICE
product: Windows
targetos: Windows
req.typenames: LINKED_DEVICE, *PLINKED_DEVICE
---

# _LINKED_DEVICE structure
The LINKED_DEVICE structure holds information that describes a linked display adapter configuration.

## Syntax
````
typedef struct _LINKED_DEVICE {
  ULONG   ChainUid;
  ULONG   NumberOfLinksInChain;
  BOOLEAN LeadLink;
} LINKED_DEVICE, *PLINKED_DEVICE;
````

## Members


`ChainUid`

A unique identifier for this chain of display adapters.

`LeadLink`

A value that indicates the leading link in the chain of linked adapters. The value is <b>TRUE</b> only for the adapter that will be allowed to enumerate child adapters. Otherwise, the value is <b>FALSE</b>.

`NumberOfLinksInChain`

The expected number of linked adapters that the operating system should enumerate.

## Remarks
Prior to a call to <a href="..\dispmprt\nc-dispmprt-dxgkddi_link_device.md">DxgkDdiLinkDevice</a>, the display miniport driver should fill the LINKED_DEVICE structure with information about the linked adapter configuration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_link_device.md">DxgkDdiLinkDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20LINKED_DEVICE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>