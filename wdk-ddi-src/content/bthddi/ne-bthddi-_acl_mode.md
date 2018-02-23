---
UID: NE:bthddi._ACL_MODE
title: "_ACL_MODE"
author: windows-driver-content
description: The ACL_MODE enumeration type is used to list the possible states of an ACL connection.
old-location: bltooth\acl_mode.htm
old-project: bltooth
ms.assetid: 90013f42-9393-4037-8d0d-13fe5d7caa0b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_ACL_MODE, bltooth.acl_mode, bthddi/ACL_MODE_ENTER_HOLD, ACL_MODE, ACL_MODE_ENTER_SNIFF, bthddi/ACL_DISCONNECTED, ACL_MODE_HOLD, bthddi/ACL_MODE_HOLD, bthddi/ACL_MODE_ENTER_PARK, bthddi/ACL_MODE_SNIFF, bthddi/ACL_MODE_ENTER_SNIFF, bth_enums_52494ea2-66f0-4c7d-8f7b-c427a21ee826.xml, bthddi/ACL_MODE_ACTIVE, ACL_MODE_ENTER_HOLD, ACL_MODE_PARK, bthddi/ACL_MODE, ACL_DISCONNECTED, ACL_MODE_SNIFF, bthddi/ACL_MODE_PARK, ACL_MODE_ENTER_ACTIVE, ACL_MODE_ENTER_PARK, ACL_MODE_ACTIVE, ACL_MODE enumeration [Bluetooth Devices], bthddi/ACL_MODE_ENTER_ACTIVE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthddi.h
apiname:
-	ACL_MODE
product: Windows
targetos: Windows
req.typenames: ACL_MODE
---

# _ACL_MODE Enumeration
The ACL_MODE enumeration type is used to list the possible states of an ACL connection.

## Syntax
````
typedef enum _ACL_MODE { 
  ACL_MODE_ACTIVE        = 0x0,
  ACL_MODE_HOLD          = 0x1,
  ACL_MODE_SNIFF         = 0x2,
  ACL_MODE_PARK          = 0x3,
  ACL_MODE_ENTER_ACTIVE  = 0x4,
  ACL_MODE_ENTER_HOLD    = 0x5,
  ACL_MODE_ENTER_SNIFF   = 0x6,
  ACL_MODE_ENTER_PARK    = 0x7,
  ACL_DISCONNECTED       = 0x8
} ACL_MODE;
````

## Constants

<table>
            
                <tr>
                    <td>ACL_DISCONNECTED</td>
                    <td>This value indicates the ACL is disconnected.</td>
                </tr>
            
                <tr>
                    <td>ACL_MODE_ACTIVE</td>
                    <td>This value indicates the ACL is in an active state.</td>
                </tr>
            
                <tr>
                    <td>ACL_MODE_ENTER_ACTIVE</td>
                    <td>This value indicates the ACL is entering an active state.</td>
                </tr>
            
                <tr>
                    <td>ACL_MODE_ENTER_HOLD</td>
                    <td>This value indicates the ACL is entering a hold state.</td>
                </tr>
            
                <tr>
                    <td>ACL_MODE_ENTER_PARK</td>
                    <td>This value indicates the ACL is entering a parked state.</td>
                </tr>
            
                <tr>
                    <td>ACL_MODE_ENTER_SNIFF</td>
                    <td>This value indicates the ACL is entering a sniffed state.</td>
                </tr>
            
                <tr>
                    <td>ACL_MODE_HOLD</td>
                    <td>This value indicates the ACL is in a hold state.</td>
                </tr>
            
                <tr>
                    <td>ACL_MODE_PARK</td>
                    <td>This value indicates the ACL is in a parked state.</td>
                </tr>
            
                <tr>
                    <td>ACL_MODE_SNIFF</td>
                    <td>This value indicates the ACL is in a sniffed state.</td>
                </tr>
</table>

## Remarks

The 
    <a href="..\bthddi\ns-bthddi-_brb_acl_get_mode.md">_BRB_ACL_GET_MODE</a> structure uses this
    enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="..\bthddi\ns-bthddi-_brb_acl_get_mode.md">_BRB_ACL_GET_MODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20ACL_MODE enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>