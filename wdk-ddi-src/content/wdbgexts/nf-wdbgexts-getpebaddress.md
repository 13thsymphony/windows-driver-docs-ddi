---
UID: NF:wdbgexts.GetPebAddress
title: GetPebAddress function
author: windows-driver-content
description: The GetPebAddress function returns the address of the process environment block (PEB) for a system process.
old-location: debugger\getpebaddress.htm
old-project: debugger
ms.assetid: 314eb897-a441-41c7-8b74-a853de70e066
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: GetPebAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetPebAddress
req.alt-loc: wdbgexts.h
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
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetPebAddress function



## -description
The <b>GetPebAddress</b> function returns the address of the process environment block (PEB) for a system process.



## -syntax

````
__inline VOID GetPebAddress(
   ULONG64    CurrentThread,
   PULONGLONG Address
);
````


## -parameters

### -param CurrentThread 

Specifies an operating system thread whose PEB's address will be returned.

In kernel-mode debugging, this is the location of the KTHREAD structure, which is returned by <a href="..\wdbgexts\nf-wdbgexts-getcurrentthreadaddr.md">GetCurrentThreadAddr</a>.  If <i>CurrentThread</i> is <b>NULL</b>, the PEB for the current process is returned.

In user-mode debugging, <i>CurrentThread</i> is ignored.


### -param Address 

Receives the address of the PEB for the current operating system process or, in kernel-mode debugging, when <i>CurrentThread</i> is not <b>NULL</b>, for the system process that contains the thread that is specified by <i>CurrentThread</i>.


## -returns
None


## -remarks
In user-mode debugging, the PEB for the current thread is returned.

In kernel-mode debugging, if <i>CurrentThread</i> is <b>NULL</b>, the PEB for the operating system process in which the last event occurred is returned.


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
<dt>Wdbgexts.h (include Wdbgexts.h or Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdbgexts\nf-wdbgexts-getcurrentthreadaddr.md">GetCurrentThreadAddr</a>
</dt>
<dt>
<a href="..\wdbgexts\nf-wdbgexts-gettebaddress.md">GetTebAddress</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20GetPebAddress function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

