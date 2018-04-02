---
UID: NS:bthddi._BRB_ACL_GET_MODE
title: "_BRB_ACL_GET_MODE"
author: windows-driver-content
description: The _BRB_ACL_GET_MODE structure describes the ACL mode for the specified remote device.
old-location: bltooth\_brb_acl_get_mode.htm
old-project: bltooth
ms.assetid: 2fe473c8-dcf9-4457-b1b1-c55b3eaa68e6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_BRB_ACL_GET_MODE, _BRB_ACL_GET_MODE structure [Bluetooth Devices], bltooth._brb_acl_get_mode, bth_structs_ce659c96-d1af-4e27-b31a-f6700ff88331.xml, bthddi/_BRB_ACL_GET_MODE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	_BRB_ACL_GET_MODE
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_ACL_GET_MODE structure
The _BRB_ACL_GET_MODE structure describes the ACL mode for the specified remote device.

## Syntax
```
struct _BRB_ACL_GET_MODE {
  BRB_HEADER Hdr;
  BTH_ADDR   BtAddress;
  ACL_MODE   AclMode;
};
```

## Members


`Hdr`

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a> structure that contains information
     about the current BRB.

`BtAddress`

The address of the remote device.

`AclMode`

A value from the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536577">ACL_MODE</a> enumeration that specifies the ACL mode of
     the remote device.

## Remarks
To get the current ACL connection state for a remote device, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536609">BRB_ACL_GET_MODE</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536577">ACL_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536609">BRB_ACL_GET_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a>