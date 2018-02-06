---
UID: NF:video.VideoPortMapMemory
title: VideoPortMapMemory function
author: windows-driver-content
description: The VideoPortMapMemory function maps a range of bus-relative physical addresses of video memory into system space or into the virtual address space of a user-mode process.
old-location: display\videoportmapmemory.htm
old-project: display
ms.assetid: c1b54ef4-93b5-41df-8a49-8b00cbd4bcee
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: video/VideoPortMapMemory, VideoPort_Functions_53fef559-5fbb-4e9a-9152-b44be67bd63c.xml, display.videoportmapmemory, VideoPortMapMemory, VideoPortMapMemory function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortMapMemory
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortMapMemory function
The <b>VideoPortMapMemory</b> function maps a range of bus-relative physical addresses of video memory into system space or into the virtual address space of a user-mode process. A video miniport driver calls <b>VideoPortMapMemory</b> when it handles IOCTL_VIDEO_MAP_VIDEO_MEMORY, IOCTL_VIDEO_SHARE_VIDEO_MEMORY, or IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES.

## Syntax

````
VP_STATUS VideoPortMapMemory(
   PVOID            HwDeviceExtension,
   PHYSICAL_ADDRESS PhysicalAddress,
   PULONG           Length,
   PULONG           InIoSpace,
   PVOID            *VirtualAddress
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`PhysicalAddress`

The bus-relative base address of the range to map.

`Length`

On input, specifies the number of bytes of video memory to map. On output, receives the size of the memory actually mapped, which might be rounded to a system-determined alignment boundary. (However, the miniport and display drivers cannot access any memory that is outside the range delimited by the input value at <i>Length</i>.)

`InIoSpace`

Pointer to a variable that indicates the location of the range. The variable can be one of the following flags or an ORed, compatible combination of these flags.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_DENSE

</td>
<td>
Obsolete.

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_IO

</td>
<td>
The address range is in I/O space, not in memory space. 

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_MEMORY

</td>
<td>
The address range is in memory space, not in I/O space. 

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_P6CACHE

</td>
<td>
The processor aggregates a sequence of write operations, sends them to a cache line, and later flushes the cache. This flag is meaningful only if VIDEO_MEMORY_SPACE_IO is not set.

Designates the video memory as write-combined (WC). For information about WC caching, see the <a href="https://msdn.microsoft.com/library/windows/hardware/dn642116">Write-Combining Memory in Video Miniport Drivers</a> website article.

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_USER_MODE

</td>
<td>
The address range should be mapped into the virtual address space of a user-mode process, not into system space. This flag is meaningful only if VIDEO_MEMORY_SPACE_IO is not set.

</td>
</tr>
</table>

`VirtualAddress`

Pointer to a variable that, on input, is either <b>NULL</b> or a handle to a user-mode process. If the input value is <b>NULL</b>, this routine maps the video memory into system space. Otherwise, this routine maps the video memory into the virtual address space of the user-mode process that is identified by the handle. On output, receives the base virtual address of the mapping.


## Return Value

<b>VideoPortMapMemory</b> returns NO_ERROR if it successfully mapped the specified range; otherwise, it returns ERROR_INVALID_PARAMETER.

## Remarks

<b>VideoPortMapMemory</b> runs in kernel mode within the same context as the user-mode thread that initiated the call.


<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a> and <b>VideoPortMapMemory</b> can both be called by the video miniport driver to map video memory into a virtual address space. If you call both of these functions to map the same physical addresses, or if you call one of the functions more than once to map the same physical addresses, you might have more than one virtual-address range that maps to the same physical-address range. In that case, you must set the VIDEO_MEMORY_SPACE_P6CACHE flag of the <i>InIoSpace</i> parameter to the same value in all of those calls.

Every universal memory architecture (UMA) display device uses a frame buffer that is located in main memory rather than on a PCI bus. In this case, do not call <b>VideoPortMapMemory</b> to map the frame buffer. To map a UMA frame buffer into system space, call <a href="..\wdm\nf-wdm-mmmapiospace.md">MmMapIoSpace</a>. To map a UMA frame buffer into the virtual address space of a user-mode process, perform the following steps:
<ol>
<li>
Call <a href="..\wdm\nf-wdm-zwopensection.md">ZwOpenSection</a> to get a handle to the operating system's physical-memory section object, which is named <b>\Device\PhysicalMemory</b>.

</li>
<li>
Call <a href="..\wdm\nf-wdm-zwmapviewofsection.md">ZwMapViewOfSection</a> to map a view of the frame buffer into the virtual address space of the current process.

</li>
</ol>The following example shows how to map a UMA frame buffer into the virtual address space of the current process.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UNICODE_STRING    UnicodeString;          // Name of the section object
OBJECT_ATTRIBUTES ObjectAttributes;       // Description for the section object
HANDLE            hPhysicalMemoryHandle;  // Handle to the section object
PHYSICAL_ADDRESS  MappedLength;           // Length of the frame buffer

PHYSICAL_ADDRESS  MappedBase;             // Base physical address (CPU-relative)
                                          // of the frame buffer

// Allocate a variable to receive the base virtual address of the view.
// Set it to NULL for input to ZwMapViewOfSection, to specify that the memory
// manager (rather than the caller) should determine the base virtual address.
PVOID pViewBase = NULL;

RtlInitUnicodeString(&amp;UnicodeString, L"\\Device\\PhysicalMemory");

InitializeObjectAttributes(
   &amp;ObjectAttributes,
   &amp;UnicodeString,
   OBJ_CASE_INSENSITIVE | OBJ_KERNEL_HANDLE,
   (HANDLE) NULL,
   (PSECURITY_DESCRIPTOR) NULL);

// Open a handle to the physical-memory section object.
ntStatus = ZwOpenSection(&amp;hPhysicalMemoryHandle, SECTION_ALL_ACCESS, &amp;ObjectAttributes);

if(NT_SUCCESS(ntStatus))
{
   ntStatus = ZwMapViewOfSection(
      hPhysicalMemoryHandle,
      NtCurrentProcess(),
      &amp;pViewBase,
      0L,
      (ULONG_PTR)MappedLength.QuadPart,
      &amp;MappedBase,
      (PULONG_PTR)(&amp;(MappedLength.QuadPart)),
      ViewUnmap,
      0,
      PAGE_READWRITE | PAGE_WRITECOMBINE);

   if(NT_SUCCESS(ntStatus))
   {
      // pViewBase holds the base virtual address of the view.
   }

   // Close the handle to the physical-memory section object.
   ZwClose(hPhysicalMemoryHandle);
}</pre>
</td>
</tr>
</table></span></div>Miniport drivers should use <b>VideoPortMapMemory</b> to manage video adapters that allow the video <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a> to be completely mapped at all times. That is, miniport drivers for adapters that are not restricted to using <a href="https://msdn.microsoft.com/bf5fa319-14ec-40df-be7a-89c07ce519ad">banks</a> to map a slice at a time can use the more efficient <b>VideoPortMapMemory</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems. Available in Windows 2000 and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\video\nf-video-videoportunmapmemory.md">VideoPortUnmapMemory</a>

<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_map_video_memory.md">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>

<a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortMapMemory function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>