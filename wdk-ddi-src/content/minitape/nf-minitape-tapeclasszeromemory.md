---
UID: NF.minitape.TapeClassZeroMemory
title: TapeClassZeroMemory function
author: windows-driver-content
description: The TapeClassZeroMemory routine fills a buffer with zeros.
old-location: storage\tapeclasszeromemory.htm
old-project: storage
ms.assetid: a1f15890-ded8-4aba-8b67-6f1fb1490178
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: TapeClassZeroMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: minitape.h
req.include-header: Minitape.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TapeClassZeroMemory
req.alt-loc: Tape.lib,Tape.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Tape.lib
req.dll: 
req.irql: 
---

# TapeClassZeroMemory function



## -description
The <b>TapeClassZeroMemory</b> routine fills a buffer with zeros.



## -syntax

````
VOID TapeClassZeroMemory(
  _Inout_ PVOID Buffer,
  _In_    ULONG BufferSize
);
````


## -parameters

### -param Buffer [in, out]

Pointer to the buffer that needs to be cleared.


### -param BufferSize [in]

Specifies the size of the buffer, in bytes.


## -returns
None


## -remarks
A tape miniclass driver calls <b>TapeClassZeroMemory</b> to zero a buffer in a portable way. A miniclass driver must use <b>TapeClassZeroMemory</b> to clear the TAPE_INIT_DATA_EX structure and CDBs before it uses them.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Minitape.h (include Minitape.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Tape.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.driverentry_of_tape_miniclass_driver">DriverEntry of Tape Miniclass Driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TapeClassZeroMemory routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

