---
UID: NE:bthddi._BRB_VERSION
title: "_BRB_VERSION"
author: windows-driver-content
description: Reserved for internal use.
old-location: bltooth\brb_version.htm
old-project: bltooth
ms.assetid: 2bd4f3f6-94a4-47a6-8c15-a8f9bef5d2b5
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: BRB_VERSION, BRB_VERSION enumeration [Bluetooth Devices], bthddi/BLUETOOTH_V1, _BRB_VERSION, BLUETOOTH_V1, bltooth.brb_version, bthddi/BLUETOOTH_V2, bthddi/BRB_VERSION, BLUETOOTH_V2, bth_enums_d14431ac-24e9-4a27-90b9-a8aef7e38769.xml
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
-	BRB_VERSION
product: Windows
targetos: Windows
req.typenames: BRB_VERSION
---

# _BRB_VERSION Enumeration
Reserved for internal use.

## Syntax
````
enum BRB_VERSION {
  BLUETOOTH_V1, 
  BLUETOOTH_V2 

};
````

## Constants

<table>
            
                <tr>
                    <td>BLUETOOTH_V1</td>
                    <td>Reserved.</td>
                </tr>
            
                <tr>
                    <td>BLUETOOTH_V2</td>
                    <td>Reserved.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="..\bthddi\nc-bthddi-pfnbth_initialize_brb.md">BthInitializeBrb</a>



<a href="..\bthddi\nc-bthddi-pfnbth_allocate_brb.md">BthAllocateBrb</a>



<a href="..\bthioctl\ni-bthioctl-ioctl_internal_bth_submit_brb.md">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>



<a href="..\bthddi\ns-bthddi-_brb.md">BRB</a>



<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BRB_VERSION Enumeration enumeration%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>