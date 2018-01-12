---
UID: NF:wdm.ExIsSoftBoot
title: ExIsSoftBoot function
author: windows-driver-content
description: Determines whether the system has gone through a soft restart.
old-location: kernel\exissoftboot.htm
old-project: kernel
ms.assetid: ff67bc75-b424-4278-b979-f67d118232aa
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExIsSoftBoot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExIsSoftBoot
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: <=APC_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExIsSoftBoot function



## -description
Determines whether the system has gone through a soft restart.



## -syntax

````
 BOOLEAN  ExIsSoftBoot(
   VOID 
);
````


## -parameters


## -returns
TRUE indicates a soft restart; FALSE otherwise.

TRUE indicates a soft restart; FALSE otherwise.

TRUE indicates a soft restart; FALSE otherwise.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

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
<dt>NtosKrnl.exe (kernel mode)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=APC_LEVEL

</td>
</tr>
</table>