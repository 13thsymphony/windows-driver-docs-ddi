---
UID: NF:wsk.WskRegister
title: WskRegister function
author: windows-driver-content
description: The WskRegister function registers a WSK application, given the application's WSK client Network Programming Interface (NPI).
old-location: netvista\wskregister.htm
old-project: netvista
ms.assetid: 340933ad-1a71-421c-b1e1-360aa9c441fd
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: WskRegister, WskRegister function [Network Drivers Starting with Windows Vista], netvista.wskregister, wsk/WskRegister, wskref_21a26aab-f817-457f-bfde-28bcf1e2c8d0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.lib: Netio.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Netio.lib
-	Netio.dll
api_name:
-	WskRegister
product: Windows
targetos: Windows
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.product: Windows 10 or later.
---


# WskRegister function
The 
  <b>WskRegister</b> function registers a WSK application, given the application's WSK client 
  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
  (NPI)</a>.

## Syntax

````
NTSTATUS WskRegister(
  _In_  PWSK_CLIENT_NPI   WskClientNpi,
  _Out_ PWSK_REGISTRATION WskRegistration
);
````

## Parameters

`WskClientNpi`

A pointer to the client NPI implemented by the WSK application.

`WskRegistration`

A pointer to a memory location that identifies a WSK application's registration instance. This
     memory location will be initialized by the 
     <b>WskRegister</b> call and will be used by the other 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571179">WSK registration functions</a>. The
     WSK application should never change the contents of this memory location directly.


## Return Value

<b>WskRegister</b> returns one of the following NTSTATUS codes:

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
The registration succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
The registration failed.

</td>
</tr>
</table>

## Remarks

A WSK client object can call this function multiple times, but a different 
    <i>WskRegistration</i> parameter must be used for each call in order to create multiple registration
    instances.

For each call to 
    <b>WskRegister</b> that returns a success code, there must be exactly one corresponding 
    <a href="..\wsk\nf-wsk-wskderegister.md">WskDeregister</a> call that uses the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskRegister</b>.

The block of memory pointed to by 
    <i>WskRegistration</i> must be kept allocated (must not be freed or go out of scope) as long as there are
    outstanding calls to other 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571179">WSK registration functions</a>.


    
    Using the 
    <b>WskRegister</b> and 
    <a href="..\wsk\nf-wsk-wskderegister.md">WskDeregister</a> functions is the preferred
    method for registering and unregistering WSK applications. The 
    <a href="https://msdn.microsoft.com/23c15c42-94aa-410b-8551-fafa8b24ad86">Network Module Registrar</a> remains
    available for compatibility.

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems.  |
| **Target Platform** | Universal |
| **Header** | wsk.h (include Wsk.h) |
| **Library** | Netio.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wsk\ns-wsk-_wsk_registration.md">WSK_REGISTRATION</a>



<a href="..\wsk\nf-wsk-wskderegister.md">WskDeregister</a>



<a href="..\wsk\ns-wsk-_wsk_client_npi.md">WSK_CLIENT_NPI</a>