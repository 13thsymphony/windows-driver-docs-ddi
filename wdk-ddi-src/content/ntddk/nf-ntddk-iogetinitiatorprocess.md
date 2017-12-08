---
UID: NF.ntddk.IoGetInitiatorProcess
title: IoGetInitiatorProcess function
author: windows-driver-content
description: The IoGetInitiatorProcess routine retrieves the process which initiated the creation of a file object if different than the process which is issuing the create.
old-location: kernel\iogetinitiatorprocess.htm
old-project: kernel
ms.assetid: 653B4FD5-4C07-420A-BE8A-CC8C46BC6F0F
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: IoGetInitiatorProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetInitiatorProcess
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
req.irql: <= DISPATCH_LEVEL
---

# IoGetInitiatorProcess function



## -description
The IoGetInitiatorProcess routine retrieves the process which initiated the creation of a file object if different than the process which is issuing the create.


## -syntax

````
PEPROCESS WINAPI IoGetInitiatorProcess(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters

### -param FileObject [in]

The file object from which to retrieve the initiator process.

## -returns
NULL if there is no initiator process. Otherwise, a pointer to which process initiated the creation of the file object.

## -remarks
A driver normally uses IoGetInitiatorProcess to determine which process has issued a request.  However, there are situations where a system component may issue a create on behalf of another process (after a successful create the component will duplicate the handle to the process).  This routine can be used if the driver must know which process the create operation is ultimately intended for. 

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
Header
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
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
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
</table>