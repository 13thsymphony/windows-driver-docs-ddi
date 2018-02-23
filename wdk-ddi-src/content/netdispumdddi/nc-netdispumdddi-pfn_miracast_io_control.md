---
UID: NC:netdispumdddi.PFN_MIRACAST_IO_CONTROL
title: PFN_MIRACAST_IO_CONTROL
author: windows-driver-content
description: Called by the user-mode display driver to send the kernel-mode display miniport driver a synchronous I/O control request.The data type of this function is PFN_MIRACAST_IO_CONTROL.
old-location: display\miracastiocontrol.htm
old-project: display
ms.assetid: df63ec18-79e0-40a6-a412-46071eb8a7fe
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.miracastiocontrol, PFN_MIRACAST_IO_CONTROL, MiracastIoControl callback function [Display Devices], MiracastIoControl, PFN_MIRACAST_IO_CONTROL, PFN_MIRACAST_IO_CONTROL, netdispumdddi/MiracastIoControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Netdispumdddi.h
apiname:
-	MiracastIoControl
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---


# PFN_MIRACAST_IO_CONTROL callback function
Called by the user-mode display driver to send the kernel-mode  display miniport driver a synchronous I/O control request.The data type of this function is <b>PFN_MIRACAST_IO_CONTROL</b>.

## Syntax

```
PFN_MIRACAST_IO_CONTROL PfnMiracastIoControl;

NTSTATUS PfnMiracastIoControl(
  HANDLE hMiracastDeviceHandle,
  BOOL HardwareAccess,
  UINT InputBufferSize,
  VOID *pInputBuffer,
  UINT OutputBufferSize,
  VOID *pOutputBuffer,
  UINT *pBytesReturned
)
{...}
```

## Parameters

`hMiracastDeviceHandle`

A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a> function.

`HardwareAccess`

A Boolean value that indicates whether this I/O control request from the user-mode display driver needs to flush all the pending GPU DMA buffers.

We don't recommend that the driver set this value to <b>TRUE</b> except when necessary, because flushing the GPU will create substantial processing overhead.

`InputBufferSize`

The size, in bytes, of the input buffer pointed to by <i>pInputBuffer</i>.

`*pInputBuffer`

A pointer to the input buffer. The <i>InputBufferSize</i> parameter specifies the size of the buffer.

`OutputBufferSize`

The size, in bytes, of the output buffer pointed to by <i>pOutputBuffer</i>.

`*pOutputBuffer`

A driver-supplied pointer to the output buffer. The <i>OutputBufferSize</i> parameter specifies the size of the buffer.

`*pBytesReturned`

An optional driver-supplied pointer to a <b>UINT</b>-type variable that holds the number of bytes that the display miniport driver returned.


## Return Value

On success, the operating system returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header.

## Remarks

If the Miracast user-mode driver calls <b>MiracastIoControl</b> when the operating system is starting a Miracast session, and if the calling thread is not the thread in which the operating system calls the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a> function, the operating system blocks the <b>MiracastIoControl</b> call until the Miracast start session is finished. If the user-mode driver calls <b>MiracastIoControl</b> in the same context as is used in  the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a> or <i>StartMiracastSession</i> functions, the operating system will process the call.

If the Miracast user-mode driver calls <b>MiracastIoControl</b> when the operating system is stopping a Miracast session, and if the calling thread is not the thread in which the operating system calls the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a> function, the operating system will fail this call. If the user-mode driver calls <b>MiracastIoControl</b> in the same context as is used in  the <i>StopMiracastSession</i> or <a href="..\netdispumdddi\nc-netdispumdddi-pfn_destroy_miracast_context.md">DestroyMiracastContext</a> functions, the operating system will process the call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | netdispumdddi.h (include Netdispumdddi.h) |

## See Also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_destroy_miracast_context.md">DestroyMiracastContext</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFN_MIRACAST_IO_CONTROL callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>