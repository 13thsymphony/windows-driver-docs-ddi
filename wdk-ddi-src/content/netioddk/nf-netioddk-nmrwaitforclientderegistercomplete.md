---
UID: NF.netioddk.NmrWaitForClientDeregisterComplete
title: NmrWaitForClientDeregisterComplete function
author: windows-driver-content
description: The NmrWaitForClientDeregisterComplete function waits for the deregistration of a client module to complete.
old-location: netvista\nmrwaitforclientderegistercomplete.htm
old-project: netvista
ms.assetid: aed0a69e-868c-4c7d-b601-003ff357da38
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NmrWaitForClientDeregisterComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: netioddk.h
req.include-header: Wsk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NmrWaitForClientDeregisterComplete
req.alt-loc: netio.lib,netio.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Netio.lib
req.dll: 
req.irql: < DISPATCH_LEVEL
---

# NmrWaitForClientDeregisterComplete function



## -description
The 
  <b>NmrWaitForClientDeregisterComplete</b> function waits for the deregistration of a client module to
  complete.


## -syntax

````
NTSTATUS NmrWaitForClientDeregisterComplete(
  _In_ HANDLE NmrClientHandle
);
````


## -parameters

### -param NmrClientHandle [in]

A handle used by the NMR to represent the registration of the client module. The NMR returns this
     handle to the client module when the client module calls the 
     <a href="netvista.nmrregisterclient">NmrRegisterClient</a> function.

## -returns
The 
     <b>NmrWaitForClientDeregisterComplete</b> function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The NMR completed deregistering the client module.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The client module called the 
       <b>NmrWaitForClientDeregisterComplete</b> function before calling the 
       <a href="netvista.nmrderegisterclient">NmrDeregisterClient</a> function, or
       the handle specified in the NmrClientHandle parameter is not a valid client handle.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 

## -remarks
A client module calls the 
    <b>NmrWaitForClientDeregisterComplete</b> function to wait for the deregistration of the client module to
    complete. A client module calls the 
    <b>NmrWaitForClientDeregisterComplete</b> function only after calling the 
    <a href="netvista.nmrderegisterclient">NmrDeregisterClient</a> function.

A client module typically calls the 
    <b>NmrWaitForClientDeregisterComplete</b> function from its 
    <a href="kernel.unload">Unload</a> function to wait until it is completely
    deregistered from the NMR before the client module is unloaded from the system. A client module must not
    return from a call to its 
    <b>Unload</b> function until after deregistration is
    complete.


<div class="alert"><b>Note</b>  If a client module uses the Windows Driver Framework, it will typically call the 
     <b>NmrWaitForClientDeregisterComplete</b> function from its 
     <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a> event callback function. In
     this situation, the client module must not return from a call to its 
     <i>EvtDriverUnload</i> function until after
     deregistration is complete.</div>
<div> </div>


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
Available in Windows Vista and later versions of the Windows operating
   systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Netioddk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Netio.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt; DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.nmrderegisterclient">NmrDeregisterClient</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NmrWaitForClientDeregisterComplete function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
