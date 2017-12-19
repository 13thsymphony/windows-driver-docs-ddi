---
UID: NF.fwpsk.FwpsAleEndpointDestroyEnumHandle0
title: FwpsAleEndpointDestroyEnumHandle0 function
author: windows-driver-content
description: The FwpsAleEndpointDestroyEnumHandle0 function destroys an endpoint enumeration handle that was created by calling FwpsAleEndpointCreateEnumHandle0.Note  FwpsAleEndpointDestroyEnumHandle0 is a specific version of FwpsAleEndpointDestroyEnumHandle.
old-location: netvista\fwpsaleendpointdestroyenumhandle0.htm
old-project: NetVista
ms.assetid: 45ec429e-d324-40c9-bedc-acd75ccb160e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FwpsAleEndpointDestroyEnumHandle0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsAleEndpointDestroyEnumHandle0
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

# FwpsAleEndpointDestroyEnumHandle0 function



## -description
The 
  <b>FwpsAleEndpointDestroyEnumHandle0</b> function destroys an endpoint enumeration handle that was created
  by calling 
  <a href="netvista.fwpsaleendpointcreateenumhandle0">
  FwpsAleEndpointCreateEnumHandle0</a>.



## -syntax

````
NTSTATUS NTAPI FwpsAleEndpointDestroyEnumHandle0(
  _In_    HANDLE engineHandle,
  _Inout_ HANDLE enumHandle
);
````


## -parameters

### -param engineHandle [in]

The handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="netvista.fwpmengineopen0">FwpmEngineOpen0</a>.


### -param enumHandle [in, out]

The enumeration handle created by a previous call to 
     <a href="netvista.fwpsaleendpointcreateenumhandle0">
     FwpsAleEndpointCreateEnumHandle0</a>.


## -returns
The 
     <b>FwpsAleEndpointDestroyEnumHandle0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
When endpoint enumeration is complete, the enumeration handle must be destroyed by calling 
    <b>FwpsAleEndpointDestroyEnumHandle0</b>.


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
Available starting with Windows 7.

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
<a href="netvista.fwpsaleendpointcreateenumhandle0">
     FwpsAleEndpointCreateEnumHandle0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20FwpsAleEndpointDestroyEnumHandle0 function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

