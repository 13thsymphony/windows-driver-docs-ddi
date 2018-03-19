---
UID: NS:ntddk._IMAGE_INFO_EX
title: "_IMAGE_INFO_EX"
author: windows-driver-content
description: Extended version of the image information structure (see IMAGE_INFO).
old-location: kernel\image_info_ex.htm
old-project: kernel
ms.assetid: 97F3D9BE-9069-4A4A-B114-FC9331510512
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PIMAGE_INFO_EX, IMAGE_INFO_EX, IMAGE_INFO_EX structure [Kernel-Mode Driver Architecture], PIMAGE_INFO_EX, PIMAGE_INFO_EX structure pointer [Kernel-Mode Driver Architecture], _IMAGE_INFO_EX, kernel.image_info_ex, ntddk/IMAGE_INFO_EX, ntddk/PIMAGE_INFO_EX"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddk.h
api_name:
-	IMAGE_INFO_EX
product: Windows
targetos: Windows
req.typenames: IMAGE_INFO_EX, *PIMAGE_INFO_EX
---

# _IMAGE_INFO_EX structure
Extended version of the image information structure (see <a href="..\ntddk\ns-ntddk-_image_info.md">IMAGE_INFO</a>).

## Syntax
````
typedef struct _IMAGE_INFO_EX {
  SIZE_T              Size;
  IMAGE_INFO          ImageInfo;
  struct _FILE_OBJECT  *FileObject;
} IMAGE_INFO_EX, *PIMAGE_INFO_EX;
````

## Members


`Size`

Specifies the size, in bytes, of the <b>IMAGE_INFO_EX</b> structure.

`ImageInfo`

An <a href="..\ntddk\ns-ntddk-_image_info.md">IMAGE_INFO</a> structure that specifies image information.

`FileObject`

Contains a pointer to the file object of the backing file for the image. The driver can take a reference to this object or use it for other operations.

## Remarks
If the <b>ExtendedInfoPresent</b> flag is set, the <b>IMAGE_INFO</b> structure is part of a larger, extended version of the image information structure. In this case, the load-image notify routine can use the <b>CONTAINING_RECORD</b> macro in the Winnt.h header file to obtain the base address of the <b>IMAGE_INFO_EX</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-_image_info.md">IMAGE_INFO</a>



<a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>



<a href="..\ntddk\nc-ntddk-pload_image_notify_routine.md">PLOAD_IMAGE_NOTIFY_ROUTINE</a>