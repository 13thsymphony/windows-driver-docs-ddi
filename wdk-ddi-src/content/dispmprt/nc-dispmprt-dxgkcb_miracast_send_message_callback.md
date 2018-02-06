---
UID: NC:dispmprt.DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK
title: DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK
author: windows-driver-content
description: Called in kernel mode when the message that was sent to the user-mode driver with a call to the DxgkCbMiracastSendMessage function has completed or has been canceled.
old-location: display\dxgkcbmiracastsendmessagecallback.htm
old-project: display
ms.assetid: 2DD7D46A-2E2B-482D-BFD6-D0AFD975107E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbmiracastsendmessagecallback, DxgkCbMiracastSendMessageCallback callback function [Display Devices], DxgkCbMiracastSendMessageCallback, DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK, DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK, dispmprt/DxgkCbMiracastSendMessageCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Dispmprt.h
apiname:
-	DxgkCbMiracastSendMessageCallback
product: Windows
targetos: Windows
req.typenames: "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---


# DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK callback function
Called in kernel mode when the message that was sent to the user-mode  driver with a call to the <a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message.md">DxgkCbMiracastSendMessage</a> function has completed or has been canceled.

## Syntax

```
DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK DxgkcbMiracastSendMessageCallback;

void DxgkcbMiracastSendMessageCallback(
  PVOID CallbackContext,
  PIO_STATUS_BLOCK pIoStatusBlock
)
{...}
```

## Parameters

`CallbackContext`

A pointer to the driver-supplied callback context. The operating system passes this context to the driver-supplied callback routine after the operation has completed.

`pIoStatusBlock`

A pointer to a driver-supplied buffer to hold the returned <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure for the completed or canceled user-mode message. This structure holds the status of the I/O call and the number of bytes that the user-mode driver wrote to the output buffer.


## Return Value

This callback function does not return a value.

## Remarks

<h3><a id="Synchronization"></a><a id="synchronization"></a><a id="SYNCHRONIZATION"></a>Synchronization</h3>This function can be called simultaneously from multiple execution threads.

The operating system guarantees that this function follows the zero level synchronization mode as defined in <a href="https://msdn.microsoft.com/2baf91e8-fafb-40e2-a24c-cbf04fe45274">Threading and Synchronization Zero Level</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a>

<a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message.md">DxgkCbMiracastSendMessage</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>