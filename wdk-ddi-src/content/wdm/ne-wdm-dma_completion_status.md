---
UID: NE:wdm.DMA_COMPLETION_STATUS
title: DMA_COMPLETION_STATUS
author: windows-driver-content
description: The DMA_COMPLETION_STATUS enumeration describes the completion status of a DMA transfer.
old-location: kernel\dma_completion_status.htm
old-project: kernel
ms.assetid: 12F6E1F5-15F9-42BE-8C47-C9A561513717
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DMA_COMPLETION_STATUS, DMA_COMPLETION_STATUS enumeration [Kernel-Mode Driver Architecture], DmaAborted, DmaCancelled, DmaComplete, DmaError, kernel.dma_completion_status, wdm/DMA_COMPLETION_STATUS, wdm/DmaAborted, wdm/DmaCancelled, wdm/DmaComplete, wdm/DmaError
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
-	Wdm.h
api_name:
-	DMA_COMPLETION_STATUS
product: Windows
targetos: Windows
req.typenames: DMA_COMPLETION_STATUS
req.product: Windows 10 or later.
---

# DMA_COMPLETION_STATUS Enumeration
The <b>DMA_COMPLETION_STATUS</b> enumeration describes the completion status of a DMA transfer.

## Syntax
````
typedef enum  { 
  DmaComplete,
  DmaAborted,
  DmaError,
  DmaCancelled
} DMA_COMPLETION_STATUS;
````

## Constants

<table>
            
                <tr>
                    <td>DmaAborted</td>
                    <td>Not used.</td>
                </tr>
            
                <tr>
                    <td>DmaCancelled</td>
                    <td>The DMA transfer did not complete successfully because the client canceled the transfer.</td>
                </tr>
            
                <tr>
                    <td>DmaComplete</td>
                    <td>The DMA transfer completed successfully.</td>
                </tr>
            
                <tr>
                    <td>DmaError</td>
                    <td>The DMA transfer did not complete successfully because an error occurred.</td>
                </tr>
</table>

## Remarks

The <i>Status</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a> routine is a <b>DMA_COMPLETION_STATUS</b>  enumeration value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DMA_COMPLETION_STATUS enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>