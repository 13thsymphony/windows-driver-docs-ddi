---
UID: NE:ucxroothub._CONTROLLER_TYPE
title: "_CONTROLLER_TYPE"
author: windows-driver-content
description: This enumeration specifies if the USB host controller is an eXtensible Host Controller Interface (xHCI) controller.
old-location: buses\_controller_type.htm
old-project: usbref
ms.assetid: E7DFBFFA-C65B-4757-8DB8-202760D6D3C6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: CONTROLLER_TYPE, ControllerTypeSoftXhci, ControllerTypeXhci, _CONTROLLER_TYPE, _CONTROLLER_TYPE enumeration [Buses], buses._controller_type, ucxroothub/ControllerTypeSoftXhci, ucxroothub/ControllerTypeXhci, ucxroothub/_CONTROLLER_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxroothub.h
api_name:
-	CONTROLLER_TYPE
product: Windows
targetos: Windows
req.typenames: CONTROLLER_TYPE
req.product: Windows 10 or later.
---

# _CONTROLLER_TYPE Enumeration
This enumeration specifies if the USB host controller is an eXtensible Host Controller Interface (xHCI) controller.

## Syntax
````
typedef enum _CONTROLLER_TYPE { 
  ControllerTypeXhci,
  ControllerTypeSoftXhci
} CONTROLLER_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>ControllerTypeSoftXhci</td>
                    <td>Indicates the USB host controller is software an xHCI controller.</td>
                </tr>
            
                <tr>
                    <td>ControllerTypeXhci</td>
                    <td>Indicates the USB host controller is an xHCI controller.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxroothub.h (include Ucxclass.h) |

## See Also

<a href="..\ucxroothub\ns-ucxroothub-_roothub_info.md">ROOTHUB_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20CONTROLLER_TYPE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>