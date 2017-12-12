---
UID: NF.fwpsk.FwpsInjectionHandleDestroy0
title: FwpsInjectionHandleDestroy0 function
author: windows-driver-content
description: The FwpsInjectionHandleDestroy0 function destroys an injection handle that was previously created by calling the FwpsInjectionHandleCreate0 function.Note  FwpsInjectionHandleDestroy0 is a specific version of FwpsInjectionHandleDestroy.
old-location: netvista\fwpsinjectionhandledestroy0.htm
old-project: netvista
ms.assetid: 5a00917b-36e8-4e06-a001-d8e6ac2e3573
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: FwpsInjectionHandleDestroy0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsInjectionHandleDestroy0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# FwpsInjectionHandleDestroy0 function



## -description
The 
  <b>FwpsInjectionHandleDestroy0</b> function destroys an injection handle that was previously created by
  calling the 
  <a href="netvista.fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a> function.



## -syntax

````
NTSTATUS FwpsInjectionHandleDestroy0(
  _In_ HANDLE injectionHandle
);
````


## -parameters

### -param injectionHandle [in]

The injection handle being destroyed.


## -returns
The 
     <b>FwpsInjectionHandleDestroy0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The injection handle was successfully destroyed.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
A callout driver calls the 
    <b>FwpsInjectionHandleDestroy0</b> function to destroy an injection handle that was previously created by
    calling the 
    <a href="netvista.fwpsinjectionhandlecreate0">
    FwpsInjectionHandleCreate0</a> function. The 
    <b>FwpsInjectionHandleDestroy0</b> function will not return to the caller until all pending injections are
    completed.


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
Available starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Fwpkclnt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsInjectionHandleDestroy0 function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

