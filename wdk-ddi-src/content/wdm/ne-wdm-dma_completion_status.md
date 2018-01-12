---
UID: NE:wdm.DMA_COMPLETION_STATUS
title: DMA_COMPLETION_STATUS
author: windows-driver-content
description: The DMA_COMPLETION_STATUS enumeration describes the completion status of a DMA transfer.
old-location: kernel\dma_completion_status.htm
old-project: kernel
ms.assetid: 12F6E1F5-15F9-42BE-8C47-C9A561513717
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: DMA_COMPLETION_STATUS, DMA_COMPLETION_STATUS
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
req.alt-api: DMA_COMPLETION_STATUS
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
req.typenames: DMA_COMPLETION_STATUS
req.product: Windows 10 or later.
---

# DMA_COMPLETION_STATUS enumeration



## -description

The <b>DMA_COMPLETION_STATUS</b> enumeration describes the completion status of a DMA transfer.



The <b>DMA_COMPLETION_STATUS</b> enumeration describes the completion status of a DMA transfer.



## -syntax

````
typedef enum  { 
  DmaComplete,
  DmaAborted,
  DmaError,
  DmaCancelled
} DMA_COMPLETION_STATUS;
````


## -enum-fields

### -field DmaComplete

The DMA transfer completed successfully.


### -field DmaAborted

Not used.


### -field DmaError

The DMA transfer did not complete successfully because an error occurred.


### -field DmaCancelled

The DMA transfer did not complete successfully because the client canceled the transfer.


## -remarks
The <i>Status</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a> routine is a <b>DMA_COMPLETION_STATUS</b>  enumeration value.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with  Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DMA_COMPLETION_STATUS enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

