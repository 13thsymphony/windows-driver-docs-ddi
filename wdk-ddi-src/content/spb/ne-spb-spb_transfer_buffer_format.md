---
UID : NE:spb.SPB_TRANSFER_BUFFER_FORMAT
title : SPB_TRANSFER_BUFFER_FORMAT
author : windows-driver-content
description : The SPB_TRANSFER_BUFFER_FORMAT enumeration specifies the format of the buffer that is described by an SPB_TRANSFER_BUFFER structure.
old-location : spb\spb_transfer_buffer_format.htm
old-project : SPB
ms.assetid : EAC78940-318D-4785-9D7E-410B8AB2F4C7
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : spb/SpbTransferBufferFormatInvalid, SpbTransferBufferFormatList, SPB_TRANSFER_BUFFER_FORMAT enumeration [Buses], spb/SpbTransferBufferFormatList, SPB.spb_transfer_buffer_format, SpbTransferBufferFormatMdl, *PSPB_TRANSFER_BUFFER_FORMAT, spb/SpbTransferBufferFormatMax, spb/SPB_TRANSFER_BUFFER_FORMAT, SpbTransferBufferFormatSimpleNonPaged, SpbTransferBufferFormatMax, spb/SpbTransferBufferFormatSimpleNonPaged, spb/SpbTransferBufferFormatSimple, SPB_TRANSFER_BUFFER_FORMAT, SpbTransferBufferFormatInvalid, SpbTransferBufferFormatSimple, spb/SpbTransferBufferFormatMdl
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : spb.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 8.
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SPB_TRANSFER_BUFFER_FORMAT, *PSPB_TRANSFER_BUFFER_FORMAT
req.product : Windows 10 or later.
---

# SPB_TRANSFER_BUFFER_FORMAT Enumeration
The <b>SPB_TRANSFER_BUFFER_FORMAT</b> enumeration specifies the format of the buffer that is described by an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406215">SPB_TRANSFER_BUFFER</a> structure.

## Syntax
````
typedef enum  { 
  SpbTransferBufferFormatInvalid,
  SpbTransferBufferFormatSimple,
  SpbTransferBufferFormatList,
  SpbTransferBufferFormatSimpleNonPaged,
  SpbTransferBufferFormatMdl,
  SpbTransferBufferFormatMax
} SPB_TRANSFER_BUFFER_FORMAT;
````

## Constants

<table>

<tr>
<td>SpbTransferBufferFormatInvalid</td>
<td>Reserved for use by the operating system.</td>
</tr>

<tr>
<td>SpbTransferBufferFormatList</td>
<td>The transfer buffer is described by a pointer to a list of buffers and a count of the number of buffers in the list.</td>
</tr>

<tr>
<td>SpbTransferBufferFormatMax</td>
<td>Reserved for use by the operating system.</td>
</tr>

<tr>
<td>SpbTransferBufferFormatMdl</td>
<td>The transfer buffer is described by a pointer to an MDL. This format value is valid only if the client that originates the I/O request is a kernel-mode driver.</td>
</tr>

<tr>
<td>SpbTransferBufferFormatSimple</td>
<td>The transfer buffer is described by a simple user-mode or kernel-mode pointer and a length.</td>
</tr>

<tr>
<td>SpbTransferBufferFormatSimpleNonPaged</td>
<td>The transfer buffer is described by a simple user-mode or kernel-mode pointer and a length. The buffer resides in nonpaged memory. This format value is valid only if the client that originates the I/O request is a kernel-mode driver.</td>
</tr>
</table>

## Remarks

The <b>Format</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406215">SPB_TRANSFER_BUFFER</a> structure is an <b>SPB_TRANSFER_BUFFER_FORMAT</b> enumeration value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | spb.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406215">SPB_TRANSFER_BUFFER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_BUFFER_FORMAT enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>