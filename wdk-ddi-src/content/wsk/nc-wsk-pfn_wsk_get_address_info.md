---
UID: NC.wsk.PFN_WSK_GET_ADDRESS_INFO
title: PFN_WSK_GET_ADDRESS_INFO
author: windows-driver-content
description: The WskGetAddressInfo function performs protocol-independent translation from a host name to a transport address.
old-location: netvista\wskgetaddressinfo.htm
old-project: NetVista
ms.assetid: 688619b9-ab0b-4459-8f1b-74815043a190
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO, PWPP_TRIAGE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WskGetAddressInfo
req.alt-loc: wsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# PFN_WSK_GET_ADDRESS_INFO callback



## -description
The 
  <i>WskGetAddressInfo</i> function performs protocol-independent translation from a host name to a transport
  address.



## -prototype

````
PFN_WSK_GET_ADDRESS_INFO WskGetAddressInfo;

NTSTATUS WSKAPI * WskGetAddressInfo(
  _In_     PWSK_CLIENT     Client,
  _In_opt_ PUNICODE_STRING NodeName,
  _In_opt_ PUNICODE_STRING ServiceName,
  _In_opt_ ULONG           NameSpace,
  _In_opt_ GUID            *Provider,
  _In_opt_ PADDRINFOEXW    Hints,
  _Out_    PADDRINFOEXW    *Result,
  _In_opt_ PEPROCESS       OwningProcess,
  _In_opt_ PETHREAD        OwningThread,
  _Inout_  PIRP            Irp
)
{ ... }
````


## -parameters

### -param Client [in]

[in] A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="netvista.wskcaptureprovidernpi">
     WskCaptureProviderNPI</a> function.


### -param NodeName [in, optional]

[in] An optional pointer to a 
     <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains a
     Unicode string that represents a host (node) name or a numeric host address string. For the Internet
     protocol, the numeric host address string is a dotted-decimal IPv4 address or an IPv6 hexadecimal
     address.


### -param ServiceName [in, optional]

[in] An optional pointer to a 
     <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains a
     Unicode string that represents a service name or a port number.


### -param NameSpace [in, optional]

[in] An optional namespace identifier that specifies the namespace providers that are queried.
     Only namespace providers that support the specified namespace can be queried successfully.


### -param Provider [in, optional]

[in] An optional pointer to a GUID of a specific namespace provider to be queried.


### -param Hints [in, optional]

[in] An optional pointer to an <a href="winsock.addrinfoex">ADDRINFOEXW</a> structure that provides hints about the type of socket
     that the caller supports.
     

The <a href="winsock.addrinfoex">ADDRINFOEXW</a> structure is defined in the 
     Ws2def.h header. It is identical to the  
     <a href="winsock.addrinfoex">addrinfoex</a> structure.

<div class="alert"><b>Important</b>  The 
     Ws2def.h header file is automatically included in 
     Wsk.h. Do not use 
     Ws2def.h directly.</div>
<div> </div>

### -param Result [out]

[out] A pointer to a caller-allocated buffer that receives a linked list of one or more
     <a href="winsock.addrinfoex">ADDRINFOEXW</a> structures that represent response information about the host.
     

<div class="alert"><b>Note</b>  The caller must call the 
     <a href="..\wsk\nc-wsk-pfn_wsk_free_address_info.md">WskFreeAddressInfo</a> function to free
     this pointer.</div>
<div> </div>
The <a href="winsock.addrinfoex">ADDRINFOEXW</a> structure is defined in the 
     Ws2def.h header. It is identical to the 
     <a href="winsock.addrinfoex">addrinfoex</a> structure.

<div class="alert"><b>Important</b>  The 
     Ws2def.h header file is automatically included in 
     Wsk.h. Do not use 
     Ws2def.h directly.</div>
<div> </div>

### -param OwningProcess [in, optional]

[in] An optional pointer to the process from which the function retrieves the security context.
     This security context indicates the user account context in which the function processes the name
     resolution request.
     

If this parameter is <b>NULL</b>, the function processes the name resolution request in the context of a
     predefined local account with minimal privileges.

If this parameter is not <b>NULL</b> and an impersonation token is in effect for the calling thread, this
     function fails and returns STATUS_INVALID_PARAMETER.


### -param OwningThread [in, optional]

[in] An optional pointer to the thread from which the function retrieves the security context.
     This parameter can be non-<b>NULL</b> only if 
     <i>OwningProcess</i> is non-<b>NULL</b>. Otherwise, this function fails and returns STATUS_INVALID_PARAMETER.
     

If this parameter is not <b>NULL</b> and an impersonation token is in effect for the calling thread, this
     function fails and returns STATUS_INVALID_PARAMETER.


### -param Irp [in, out]

[in/out] A pointer to an I/O request packet (IRP) to use to complete the request asynchronously.
     Upon completion of the request, 
     <i>Irp</i> -&gt;
     <b>Iostatus.Information</b> will hold the returned status code.


## -returns
<b>WskGetAddressInfo</b> returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was specified.
<dl>
<dt><b>STATUS_NO_MATCH</b></dt>
</dl>The host name cannot be resolved.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function completed successfully. If the WSK application specified a pointer to an IRP in the
       
       <i>Irp</i> parameter, the IRP will be completed with a success status.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The WSK subsystem could not complete the function immediately. The WSK subsystem will complete
       the IRP after it has completed the control operation. The status of the control operation will be
       returned in the 
       <b>IoStatus.Status</b> field of the IRP.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. The IRP will be completed with failure status.

 


## -remarks
The process to which the 
    <i>OwningProcess</i> parameter points, or the thread to which the 
    <i>OwningThread</i> process points, indicates the security context for this function. The user account
    that is indicated by the security context indicates the context for the function's name resolution
    request.


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
Available in Windows 7 and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a>
</dt>
<dt>
<a href="netvista.wskcaptureprovidernpi">WskCaptureProviderNPI</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_free_address_info.md">WskFreeAddressInfo</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20PFN_WSK_GET_ADDRESS_INFO callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

