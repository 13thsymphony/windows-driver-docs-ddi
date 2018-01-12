---
UID: NF:video.VideoPortInterlockedExchange
title: VideoPortInterlockedExchange function
author: windows-driver-content
description: The VideoPortInterlockedExchange function locks or unlocks a block of memory by setting a user-defined lock variable to TRUE or FALSE, respectively. It returns the previously-held value of the lock variable.
old-location: display\videoportinterlockedexchange.htm
old-project: display
ms.assetid: a01f1552-7bc5-4ae7-a195-c4cfc3553595
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortInterlockedExchange
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
req.alt-api: VideoPortInterlockedExchange
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: Any level
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortInterlockedExchange function



## -description
The <b>VideoPortInterlockedExchange</b> function locks or unlocks a block of memory by setting a user-defined lock variable to <b>TRUE</b> or <b>FALSE</b>, respectively. It returns the previously-held value of the lock variable.



## -syntax

````
LONG FASTCALL VideoPortInterlockedExchange(
  _Inout_ PLONG Target,
  _In_    LONG  Value
);
````


## -parameters

### -param Target [in, out]

Pointer to a user-defined lock variable that is used to control access to a memory buffer. 


### -param Value [in]

Specifies the value to be stored in <i>Target</i>, which indicates whether the memory buffer is to be locked or unlocked. Use <b>TRUE</b> to lock the memory buffer, and <b>FALSE</b> to unlock the memory buffer. 


## -returns
<b>VideoPortInterlockedExchange</b> returns the value that <i>Target</i> had prior to the function call.


## -remarks
<b>VideoPortInterlockedExchange</b> can be used to prevent DMA common-buffer contention in multiple-processor systems.

When the buffer is not being read from or written to, the lock variable should have a value of <b>FALSE</b>. A subsequent call to <b>VideoPortInterlockedExchange</b> with its <i>Target</i> parameter set to <b>TRUE</b> resets the lock variable to <b>TRUE</b>, after which this function returns <b>FALSE</b>. The buffer is now locked, preventing access by other threads. When the current operations on the buffer are complete, unlock the buffer with a call to <b>VideoPortInterlockedExchange</b> with its <i>Target</i> parameter set to <b>FALSE</b>. 


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
Version

</th>
<td width="70%">
Available in Windows 2000 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\video\nf-video-videoportinterlockedincrement.md">VideoPortInterlockedIncrement</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportinterlockeddecrement.md">VideoPortInterlockedDecrement</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportgetcommonbuffer.md">VideoPortGetCommonBuffer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortInterlockedExchange function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

