---
UID: NS:ntdd8042._INTERNAL_I8042_START_INFORMATION
title: "_INTERNAL_I8042_START_INFORMATION"
author: windows-driver-content
description: INTERNAL_I8042_START_INFORMATION specifies the interrupt object that an optional, vendor-supplied, upper-level filter device driver can use to synchronize its operation with an I8042prt ISR.
old-location: hid\internal_i8042_start_information.htm
old-project: hid
ms.assetid: 8ceaa9de-195f-4a89-bc3e-323256097248
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PINTERNAL_I8042_START_INFORMATION, INTERNAL_I8042_START_INFORMATION, INTERNAL_I8042_START_INFORMATION structure [Human Input Devices], PINTERNAL_I8042_START_INFORMATION, PINTERNAL_I8042_START_INFORMATION structure pointer [Human Input Devices], _INTERNAL_I8042_START_INFORMATION, hid.internal_i8042_start_information, i8042ref_bf7bcffd-5c6b-47b4-be53-2b543990b2fa.xml, ntdd8042/INTERNAL_I8042_START_INFORMATION, ntdd8042/PINTERNAL_I8042_START_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntdd8042.h
api_name:
-	INTERNAL_I8042_START_INFORMATION
product: Windows
targetos: Windows
req.typenames: INTERNAL_I8042_START_INFORMATION, *PINTERNAL_I8042_START_INFORMATION
---

# _INTERNAL_I8042_START_INFORMATION structure
INTERNAL_I8042_START_INFORMATION specifies the <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">interrupt object</a> that an optional, vendor-supplied, upper-level filter device driver can use to synchronize its operation with an I8042prt ISR.

## Syntax
````
typedef struct _INTERNAL_I8042_START_INFORMATION {
  ULONG       Size;
  PKINTERRUPT InterruptObject;
  ULONG       Reserved[8];
} INTERNAL_I8042_START_INFORMATION, *PINTERNAL_I8042_START_INFORMATION;
````

## Members


`InterruptObject`

Pointer to an interrupt object. I8042prt supplies the interrupt object.

`Reserved`

Reserved for future use.

`Size`

Specifies the size, in bytes, of an INTERNAL_I8042_START_INFORMATION structure.

## Remarks
This structure is used with <a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_keyboard_start_information.md">IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION</a> and <a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_mouse_start_information.md">IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION</a> requests.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdd8042.h (include Ntdd8042.h) |

## See Also

<a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_mouse_start_information.md">IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION</a>



<a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_keyboard_start_information.md">IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20INTERNAL_I8042_START_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>