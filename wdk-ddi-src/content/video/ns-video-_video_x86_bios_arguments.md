---
UID : NS:video._VIDEO_X86_BIOS_ARGUMENTS
title : _VIDEO_X86_BIOS_ARGUMENTS
author : windows-driver-content
description : The VIDEO_x86_BIOS_ARGUMENTS structure is used to support full-screen MS-DOS application INT10 calls. It contains seven of the high-end x86 microprocessor registers.
old-location : display\video_x86_bios_arguments.htm
old-project : display
ms.assetid : c0404803-d8a5-4698-a725-12c659cbcaab
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : PVIDEO_X86_BIOS_ARGUMENTS structure pointer [Display Devices], display.video_x86_bios_arguments, video/PVIDEO_X86_BIOS_ARGUMENTS, Video_Structs_6e82199c-1448-483c-ab53-73590564b165.xml, PVIDEO_X86_BIOS_ARGUMENTS, *PVIDEO_X86_BIOS_ARGUMENTS, video/VIDEO_X86_BIOS_ARGUMENTS, VIDEO_x86_BIOS_ARGUMENTS, VIDEO_X86_BIOS_ARGUMENTS structure [Display Devices], VIDEO_x86_BIOS_ARGUMENTS structure [Display Devices], _VIDEO_X86_BIOS_ARGUMENTS, VIDEO_X86_BIOS_ARGUMENTS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : video.h
req.include-header : Video.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VIDEO_X86_BIOS_ARGUMENTS, *PVIDEO_X86_BIOS_ARGUMENTS
req.product : Windows 10 or later.
---

# _VIDEO_X86_BIOS_ARGUMENTS structure
The VIDEO_x86_BIOS_ARGUMENTS structure is used to support full-screen MS-DOS application INT10 calls. It contains seven of the high-end x86 microprocessor registers.

## Syntax
````
typedef struct _VIDEO_X86_BIOS_ARGUMENTS {
  ULONG Eax;
  ULONG Ebx;
  ULONG Ecx;
  ULONG Edx;
  ULONG Esi;
  ULONG Edi;
  ULONG Ebp;
} VIDEO_X86_BIOS_ARGUMENTS, *PVIDEO_X86_BIOS_ARGUMENTS;
````

## Members


`Eax`



`Ebp`

Are the seven x86 microprocessor registers.

`Ebx`



`Ecx`



`Edi`



`Edx`



`Esi`



## Remarks
MS-DOS INT10s are usually "set mode" requests for the video adapter. Each value is put in the appropriate register and an INT10 call is performed by <a href="..\video\nf-video-videoportint10.md">VideoPortInt10</a>.

A miniport driver should <i>not</i> set a segment:offset-type pointer in any member of this structure. Such an address is interpreted as an unsigned DWORD value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |

## See Also

<a href="..\video\nf-video-videoportint10.md">VideoPortInt10</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_x86_BIOS_ARGUMENTS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>