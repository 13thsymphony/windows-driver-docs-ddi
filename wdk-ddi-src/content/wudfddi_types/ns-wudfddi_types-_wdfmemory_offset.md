---
UID: NS.WUDFDDI_TYPES._WDFMEMORY_OFFSET
title: _WDFMEMORY_OFFSET
author: windows-driver-content
description: The WDFMEMORY_OFFSET structure describes the location and size of information that is accessed within a memory block.
old-location: wdf\wdfmemory_offset_umdf.htm
old-project: wdf
ms.assetid: 960710f7-15b1-4815-a33a-0e903d0a4193
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDFMEMORY_OFFSET, *PWDFMEMORY_OFFSET, WDFMEMORY_OFFSET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDFMEMORY_OFFSET
req.alt-loc: Wudfddi_types.h
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
req.product: Windows 10 or later.
---

# _WDFMEMORY_OFFSET structure



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

      The <a href="wdf.wdfmemory_offset">WDFMEMORY_OFFSET</a> structure describes the location and size of information that is accessed within a memory block.


## -syntax

````
typedef struct _WDFMEMORY_OFFSET {
  ULONG_PTR BufferOffset;
  ULONG_PTR BufferLength;
} WDFMEMORY_OFFSET, *PWDFMEMORY_OFFSET;
````


## -struct-fields

### -field BufferOffset

The offset, in bytes, into the memory block where information is first accessed. 

### -field BufferLength

The size, in bytes, of the information that is accessed in the memory block. 

## -remarks
A UMDF driver supplies a pointer to a <a href="wdf.wdfmemory_offset">WDFMEMORY_OFFSET</a> structure to the <a href="wdf.iwdfmemory_copyfrommemory">IWDFMemory::CopyFromMemory</a> method to describe information to copy from a memory block.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wudfddi_types.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.iwdfmemory_copyfrommemory">IWDFMemory::CopyFromMemory</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDFMEMORY_OFFSET structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
