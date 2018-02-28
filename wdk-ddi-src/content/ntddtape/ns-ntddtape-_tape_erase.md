---
UID: NS:ntddtape._TAPE_ERASE
title: "_TAPE_ERASE"
author: windows-driver-content
description: The TAPE_ERASE structure is used in conjunction with the IOCTL_TAPE_ERASE request to erase the current tape partition.
old-location: storage\tape_erase.htm
old-project: storage
ms.assetid: dc17efe6-9183-4908-8ca5-69c6ae38db6d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PTAPE_ERASE, PTAPE_ERASE, PTAPE_ERASE structure pointer [Storage Devices], TAPE_ERASE, TAPE_ERASE structure [Storage Devices], _TAPE_ERASE, ntddtape/PTAPE_ERASE, ntddtape/TAPE_ERASE, storage.tape_erase, structs-tape_56c14eca-358e-438f-9ff4-06345d2b2434.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddtape.h
req.include-header: Ntddtape.h, Minitape.h
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
-	ntddtape.h
api_name:
-	TAPE_ERASE
product: Windows
targetos: Windows
req.typenames: TAPE_ERASE, *PTAPE_ERASE
---

# _TAPE_ERASE structure
The TAPE_ERASE structure is used in conjunction with the <a href="..\ntddtape\ni-ntddtape-ioctl_tape_erase.md">IOCTL_TAPE_ERASE</a> request to erase the current tape partition.

## Syntax
````
typedef struct _TAPE_ERASE {
  ULONG   Type;
  BOOLEAN Immediate;
} TAPE_ERASE, *PTAPE_ERASE;
````

## Members


`Immediate`

Indicates that the target device should return status immediately, when set to <b>TRUE</b>. When this member is set to <b>FALSE</b>, the device should return status after the operation is complete.

`Type`

Indicates the type of erasure to perform. When this member is set to TAPE_ERASE_LONG, the tape partition is overwritten with a filler pattern. When it is set to TAPE_ERASE_SHORT, an end-of-recorded-data mark is written to the current position.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddtape.h (include Ntddtape.h, Minitape.h) |

## See Also

<a href="..\ntddtape\ni-ntddtape-ioctl_tape_erase.md">IOCTL_TAPE_ERASE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_ERASE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>