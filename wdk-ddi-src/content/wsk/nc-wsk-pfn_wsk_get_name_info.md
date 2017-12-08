---
UID: NC.wsk.PFN_WSK_GET_NAME_INFO
title: PFN_WSK_GET_NAME_INFO
author: windows-driver-content
description: The WskGetNameInfo function provides protocol-independent translation from a transport address to a host name.
old-location: netvista\wskgetnameinfo.htm
old-project: netvista
ms.assetid: 99e10a70-90a7-4d96-ae5f-ba82d8c4c1a8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO
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
req.alt-api: WskGetNameInfo
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

# PFN_WSK_GET_NAME_INFO callback



## -description
The 
  <b>WskGetNameInfo</b> function provides protocol-independent translation from a transport address to a host
  name.


## -prototype

````
NTSTATUS WSKAPI * WskGetNameInfo(
  _In_      PWSK_CLIENT     Client,
  _In_      PSOCKADDR       SockAddr,
  _In_      ULONG           SockAddrLength,
  _Out_opt_ PUNICODE_STRING NodeName,
  _Out_opt_ PUNICODE_STRING ServiceName,
  _In_      ULONG           Flags,
  _In_opt_  PEPROCESS       OwningProcess,
  _In_opt_  PETHREAD        OwningThread,
  _Inout_   PIRP            Irp
);
````


## -parameters

### -param Client [in]

[in] A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="netvista.wskcaptureprovidernpi">
     WskCaptureProviderNPI</a> function.

### -param SockAddr [in]

[in] A pointer to a 
     <a href="netvista.sockaddr">SOCKADDR</a> structure that contains the IP address
     and port number of the socket.

### -param SockAddrLength [in]

[in] Specifies the length, in bytes, of the buffer pointed to by the 
     <i>SockAddr</i> parameter. The value of 
     <i>SockAddrLength</i> should not exceed the size of the 
     <a href="..\ntifs\ns-ntifs-sockaddr_storage.md">SOCKADDR_STORAGE</a> structure.

### -param NodeName [out, optional]

[out] An optional pointer to a 
     <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains a
     Unicode string that represents a host (node) name. On success, the Unicode host name is written as a
     Fully Qualified Domain Name (FQDN) by default. The caller must provide a UNICODE_STRING buffer large
     enough to hold the Unicode host name, which includes the terminating NULL character. If the 
     <i>NodeBuffer</i> parameter is <b>NULL</b>, the caller does not want to receive a host name string. 
     <i>NodeBuffer</i> and 
     <i>ServiceBuffer</i> must not both be <b>NULL</b>.

### -param ServiceName [out, optional]

[out] An optional pointer to a 
     <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains a
     Unicode string that represents a service name associated with the port number. The caller must provide a
     UNICODE_STRING buffer large enough to hold the Unicode service name, which includes the terminating NULL
     character. If the 
     <i>NodeBuffer</i> parameter is <b>NULL</b>, the caller does not want to receive a service name string. 
     <i>NodeBuffer</i> and 
     <i>ServiceBuffer</i> must not both be <b>NULL</b>.

### -param Flags [in]

[in] A ULONG value that is used to customize the processing of this function.
     
The following flags are available:


### -param NI_DGRAM

Indicates that the service is a datagram service. This flag is necessary for the few services
       that provide different port numbers for UDP and TCP service.

### -param NI_NAMEREQD

Indicates that a host name that cannot be resolved by DNS results in an error.

### -param NI_NOFQDN

Results in a local host having only its Relative Distinguished Name (RDN) returned in the 
       <i>NodeName</i> parameter.

### -param NI_NUMERICHOST

Indicates that the function returns the numeric form of the host name instead of its name, a
       reverse DNS lookup. The numeric form of the host name is also returned if the host name cannot be
       resolved by DNS.

### -param NI_NUMERICSERV

Indicates that the function returns the port number of the service instead of its name. Also, if
       a host name is not found for an IP address (127.0.0.2, for example), the host name is returned as the
       IP address.
</dd>
</dl>

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
<b>WskGetNameInfo</b> returns one of the following NTSTATUS codes:
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
<a href="netvista.sockaddr">SOCKADDR</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-sockaddr_storage.md">SOCKADDR_STORAGE</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a>
</dt>
<dt>
<a href="netvista.wskcaptureprovidernpi">WskCaptureProviderNPI</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_get_address_info.md">WskGetAddressInfo</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_GET_NAME_INFO callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
