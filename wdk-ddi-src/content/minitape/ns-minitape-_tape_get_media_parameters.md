---
UID: NS:minitape._TAPE_GET_MEDIA_PARAMETERS
title: "_TAPE_GET_MEDIA_PARAMETERS"
author: windows-driver-content
description: The TAPE_GET_MEDIA_PARAMETERS structure is used in conjunction with the TapeMiniGetMediaParameters routine to retrieve tape media parameters.
old-location: storage\tape_get_media_parameters.htm
old-project: storage
ms.assetid: 3e12c431-4f6d-4d07-be52-e4809e8bc798
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PTAPE_GET_MEDIA_PARAMETERS, PTAPE_GET_MEDIA_PARAMETERS, PTAPE_GET_MEDIA_PARAMETERS structure pointer [Storage Devices], TAPE_GET_MEDIA_PARAMETERS, TAPE_GET_MEDIA_PARAMETERS structure [Storage Devices], _TAPE_GET_MEDIA_PARAMETERS, ntddtape/PTAPE_GET_MEDIA_PARAMETERS, ntddtape/TAPE_GET_MEDIA_PARAMETERS, storage.tape_get_media_parameters, structs-tape_19ce668d-65dd-40d6-a668-d34e540cc686.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: minitape.h
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
-	TAPE_GET_MEDIA_PARAMETERS
product: Windows
targetos: Windows
req.typenames: TAPE_GET_MEDIA_PARAMETERS, *PTAPE_GET_MEDIA_PARAMETERS
---

# _TAPE_GET_MEDIA_PARAMETERS structure
The TAPE_GET_MEDIA_PARAMETERS structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567937">TapeMiniGetMediaParameters</a> routine to retrieve tape media parameters.

## Syntax
````
typedef struct _TAPE_GET_MEDIA_PARAMETERS {
  LARGE_INTEGER Capacity;
  LARGE_INTEGER Remaining;
  ULONG         BlockSize;
  ULONG         PartitionCount;
  BOOLEAN       WriteProtected;
} TAPE_GET_MEDIA_PARAMETERS, *PTAPE_GET_MEDIA_PARAMETERS;
````

## Members


`BlockSize`

Indicates the block size, in bytes, or zero if the drive is using variable block size.

`Capacity`

Indicates the total number of bytes of user data the tape can hold.

`PartitionCount`

Indicates the number of partitions on the tape. If the tape is not partitioned, <b>PartitionCount</b> is 1.

`Remaining`

Indicates the number of bytes from the current position to the end of the tape.

`WriteProtected`

Is set to <b>TRUE</b> if the tape is write-protected.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | minitape.h (include Ntddtape.h, Minitape.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567937">TapeMiniGetMediaParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_GET_MEDIA_PARAMETERS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>