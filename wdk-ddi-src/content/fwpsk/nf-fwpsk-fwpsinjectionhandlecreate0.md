---
UID: NF:fwpsk.FwpsInjectionHandleCreate0
title: FwpsInjectionHandleCreate0 function
author: windows-driver-content
description: The FwpsInjectionHandleCreate0 function creates a handle that can be used by packet injection functions to inject packet or stream data into the TCP/IP network stack and by the FwpsQueryPacketInjectionState0 function to query the packet injection state.Note  FwpsInjectionHandleCreate0 is a specific version of FwpsInjectionHandleCreate. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsinjectionhandlecreate0.htm
old-project: netvista
ms.assetid: 61cee8ef-1070-46d4-a541-94a9f09b593b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: FwpsInjectionHandleCreate0, FwpsInjectionHandleCreate0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsInjectionHandleCreate0, netvista.fwpsinjectionhandlecreate0, wfp_ref_2_funct_3_fwps_I_24f21d21-bf9c-4f77-9630-2c589b18aca4.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsInjectionHandleCreate0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---


# FwpsInjectionHandleCreate0 function
The 
  <b>FwpsInjectionHandleCreate0</b> function creates a handle that can be used by 
  <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a> to inject
  packet or stream data into the TCP/IP network stack and by the 
  <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">FwpsQueryPacketInjectionState0</a> function to query the packet injection state.
<div class="alert"><b>Note</b>  <b>FwpsInjectionHandleCreate0</b> is a specific version of <b>FwpsInjectionHandleCreate</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

````
NTSTATUS NTAPI FwpsInjectionHandleCreate0(
  _In_opt_ ADDRESS_FAMILY addressFamily,
  _In_     UINT32         flags,
  _Out_    HANDLE         *injectionHandle
);
````

## Parameters

`addressFamily`

The address family for which the injection handle is being created. This can be one of the
     following address families:
     





#### AF_UNSPEC

The address family is unspecified.



#### AF_INET

The IPv4 address family.



#### AF_INET6

The IPv6 address family.

For transport, stream, and forward injections, this parameter is optional and can be set to
     AF_UNSPEC, which indicates an unspecified address family. This value is defined in 
     Ws2def.h.

`flags`

A flag value set by a callout driver to indicate the type of data to be injected. This flag can have
     one or more of the following values: 
     





#### FWPS_INJECTION_TYPE_FORWARD

Packet data will be injected by calling the 
       <a href="..\fwpsk\nf-fwpsk-fwpsinjectforwardasync0.md">
       FwpsInjectForwardAsync0</a> function.



#### FWPS_INJECTION_TYPE_NETWORK

Network data will be injected by calling either the 
       <a href="..\fwpsk\nf-fwpsk-fwpsinjectnetworkreceiveasync0.md">
       FwpsInjectNetworkReceiveAsync0</a> function or the 
       <a href="..\fwpsk\nf-fwpsk-fwpsinjectnetworksendasync0.md">
       FwpsInjectNetworkSendAsync0</a> function.



#### FWPS_INJECTION_TYPE_STREAM

Stream data will be injected by calling the 
       <a href="..\fwpsk\nf-fwpsk-fwpsstreaminjectasync0.md">
       FwpsStreamInjectAsync0</a> function.



#### FWPS_INJECTION_TYPE_TRANSPORT

Transport data will be injected by calling either the 
       <a href="..\fwpsk\nf-fwpsk-fwpsinjecttransportreceiveasync0.md">
       FwpsInjectTransportReceiveAsync0</a> function or the 
       <a href="..\fwpsk\nf-fwpsk-fwpsinjecttransportsendasync0.md">
       FwpsInjectTransportSendAsync0</a> function.

 To create an injection handle to be used by multiple injection functions, combine the
     injection type bits with bitwise OR operations. If the flag value is set to zero, the resulting
     injection handle can be used for transport, stream, and forward injections.

`injectionHandle`

A pointer to a variable that receives the handle.


## Return Value

The 
     <b>FwpsInjectionHandleCreate0</b> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The injection handle was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_TCPIP_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The TCP/IP network stack is not ready. A callout driver should call the 
       <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a> function again at a later time to create an injection handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>

## Remarks

A callout driver calls the 
    <b>FwpsInjectionHandleCreate0</b> function to create a handle that can be used for injecting packet or
    stream data into the TCP/IP network stack and to query the packet injection state. A callout driver
    passes the created handle to the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection
    functions</a> and 
    <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">
    FwpsQueryPacketInjectionState0</a>.

After a callout driver has finished using an injection handle, it must call the 
    <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandledestroy0.md">FwpsInjectionHandleDestroy0</a> function to destroy the handle. If pending injections have not yet
    completed, this function will wait for their completion before returning.

When injections are being made to the network layer and both IPv4 and IPv6 address families are being
    filtered, the callout driver must create two injection handles by calling the 
    <b>FwpsInjectionHandleCreate0</b> function twice: one call with 
    <i>addressFamily</i> set to AF_INET, and a second call with 
    <i>addressFamily</i> set to AF_INET6.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista.  |
| **Target Platform** | Universal |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** | Fwpkclnt.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">Packet Injection Functions</a>



<a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">
   FwpsQueryPacketInjectionState0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandledestroy0.md">FwpsInjectionHandleDestroy0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsInjectionHandleCreate0 function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>