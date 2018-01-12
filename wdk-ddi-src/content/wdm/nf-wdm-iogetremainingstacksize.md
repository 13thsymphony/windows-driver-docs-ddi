---
UID: NF:wdm.IoGetRemainingStackSize
title: IoGetRemainingStackSize function
author: windows-driver-content
description: The IoGetRemainingStackSize routine returns the current amount of available kernel-mode stack space.
old-location: kernel\iogetremainingstacksize.htm
old-project: kernel
ms.assetid: 5e257b72-fe16-49a0-9232-9c791a88e903
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoGetRemainingStackSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetRemainingStackSize
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
req.irql: See Remarks section.
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetRemainingStackSize function



## -description
The <b>IoGetRemainingStackSize</b> routine returns the current amount of available kernel-mode stack space.



## -syntax

````
ULONG_PTR IoGetRemainingStackSize(void);
````


## -parameters


## -returns
<b>IoGetRemainingStackSize</b> returns the number of bytes of stack space in the current thread context.

<b>IoGetRemainingStackSize</b> returns the number of bytes of stack space in the current thread context.

<b>IoGetRemainingStackSize</b> returns the number of bytes of stack space in the current thread context.


## -remarks
Highest-level drivers, such as file systems, can call this routine, particularly drivers that use recursive code paths. Such a driver would call <b>IoGetRemainingStackSize</b> before launching a recursion to determine whether it should continue processing on an alternate code path.

For Windows Server 2003 Service Pack 1 (SP1) and later versions of Windows, callers of <b>IoGetRemainingStackSize</b> can be running at any IRQL. For earlier versions of Windows, the caller must be running at IRQL &lt;= APC_LEVEL.


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
Available starting with Windows 2000.

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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
See Remarks section.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iogetinitialstack.md">IoGetInitialStack</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iogetstacklimits.md">IoGetStackLimits</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetRemainingStackSize routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

