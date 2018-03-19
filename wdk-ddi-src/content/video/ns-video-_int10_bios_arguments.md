---
UID: NS:video._INT10_BIOS_ARGUMENTS
title: "_INT10_BIOS_ARGUMENTS"
author: windows-driver-content
description: The INT10_BIOS_ARGUMENTS structure is used to support full-screen MS-DOS application INT10 calls. It contains nine of the high-end x86 microprocessor registers.
old-location: display\int10_bios_arguments.htm
old-project: display
ms.assetid: 66fc9bd4-da47-4cd1-baf2-b536272ea28e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PINT10_BIOS_ARGUMENTS, INT10_BIOS_ARGUMENTS, INT10_BIOS_ARGUMENTS structure [Display Devices], PINT10_BIOS_ARGUMENTS, PINT10_BIOS_ARGUMENTS structure pointer [Display Devices], Video_Structs_986b625a-f1b4-401e-b2db-99463c21e8f9.xml, _INT10_BIOS_ARGUMENTS, display.int10_bios_arguments, video/INT10_BIOS_ARGUMENTS, video/PINT10_BIOS_ARGUMENTS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	INT10_BIOS_ARGUMENTS
product: Windows
targetos: Windows
req.typenames: INT10_BIOS_ARGUMENTS, *PINT10_BIOS_ARGUMENTS
req.product: Windows 10 or later.
---

# _INT10_BIOS_ARGUMENTS structure
The INT10_BIOS_ARGUMENTS structure is used to support full-screen MS-DOS application INT10 calls. It contains nine of the high-end x86 microprocessor registers.

## Syntax
````
typedef struct _INT10_BIOS_ARGUMENTS {
  ULONG  Eax;
  ULONG  Ebx;
  ULONG  Ecx;
  ULONG  Edx;
  ULONG  Esi;
  ULONG  Edi;
  ULONG  Ebp;
  USHORT SegDs;
  USHORT SegEs;
} INT10_BIOS_ARGUMENTS, *PINT10_BIOS_ARGUMENTS;
````

## Members


`Eax`



`Ebx`



`Ecx`



`Edx`



`Esi`



`Edi`



`Ebp`

Are seven of the x86 microprocessor registers.

`SegDs`



`SegEs`

Are two of the x86 microprocessor segment registers.

## Remarks
The first seven members of the INT10_BIOS_ARGUMENTS structure are identical to those of the <a href="..\video\ns-video-_video_x86_bios_arguments.md">VIDEO_x86_BIOS_ARGUMENTS</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | video.h (include Video.h) |

## See Also

<a href="..\video\ns-video-_video_x86_bios_arguments.md">VIDEO_x86_BIOS_ARGUMENTS</a>



<a href="..\video\nc-video-pint10_call_bios.md">Int10CallBios</a>