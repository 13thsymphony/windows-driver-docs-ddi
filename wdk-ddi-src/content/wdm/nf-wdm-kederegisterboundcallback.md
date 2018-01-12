---
UID: NF:wdm.KeDeregisterBoundCallback
title: KeDeregisterBoundCallback function
author: windows-driver-content
description: The KeDeregisterBoundCallback routine deregisters a user-mode bound exception callback registered by KeRegisterBoundCallback.
old-location: kernel\kederegisterboundcallback.htm
old-project: kernel
ms.assetid: 697709D4-DBB7-4CB4-83A1-89E8BAFD68DA
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeDeregisterBoundCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeDeregisterBoundCallback
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeDeregisterBoundCallback function



## -description
The <b>KeDeregisterBoundCallback</b> routine deregisters a user-mode bound exception callback registered by <a href="..\wdm\nf-wdm-keregisterboundcallback.md">KeRegisterBoundCallback</a>.



## -syntax

````
NTSTATUS KeDeregisterBoundCallback(
  _In_ PVOID Handle
);
````


## -parameters

### -param Handle [in]

Specifies the value returned by <a href="..\wdm\nf-wdm-keregisterboundcallback.md">KeRegisterBoundCallback</a> when the callback was registered. 


## -returns
The <b>KeDeregisterBoundCallback</b> routine returns STATUS_SUCCESS if the callback is successfully removed. It returns STATUS_INVALID_HANDLE if no callback matching the provided <i>Handle</i> value is found.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-keregisterboundcallback.md">KeRegisterBoundCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeDeregisterBoundCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

