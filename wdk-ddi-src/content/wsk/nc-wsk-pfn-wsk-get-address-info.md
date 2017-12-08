---
UID: NC.wsk.PFN_WSK_GET_ADDRESS_INFO
title: PFN_WSK_GET_ADDRESS_INFO
author: windows-driver-content
description: The WskGetAddressInfo function performs protocol-independent translation from a host name to a transport address.
old-location: netvista\wskgetaddressinfo.htm
old-project: netvista
ms.assetid: 688619b9-ab0b-4459-8f1b-74815043a190
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WPP_TRIAGE_INFO, WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
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
req.iface: 
req.product: Windows 10 or later.
---

# PFN_WSK_GET_ADDRESS_INFO callback



## -description
<p>The 
  <i>WskGetAddressInfo</i> function performs protocol-independent translation from a host name to a transport
  address.</p>


## -prototype

````
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
);
````


## -parameters
<dl>

### -param Client [in]

<dd>
<p>[in] A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">
     WskCaptureProviderNPI</a> function.</p>
</dd>

### -param NodeName [in, optional]

<dd>
<p>[in] An optional pointer to a 
     <a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a> structure that contains a
     Unicode string that represents a host (node) name or a numeric host address string. For the Internet
     protocol, the numeric host address string is a dotted-decimal IPv4 address or an IPv6 hexadecimal
     address.</p>
</dd>

### -param ServiceName [in, optional]

<dd>
<p>[in] An optional pointer to a 
     <a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a> structure that contains a
     Unicode string that represents a service name or a port number.</p>
</dd>

### -param NameSpace [in, optional]

<dd>
<p>[in] An optional namespace identifier that specifies the namespace providers that are queried.
     Only namespace providers that support the specified namespace can be queried successfully.</p>
</dd>

### -param Provider [in, optional]

<dd>
<p>[in] An optional pointer to a GUID of a specific namespace provider to be queried.</p>
</dd>

### -param Hints [in, optional]

<dd>
<p>[in] An optional pointer to an <a href="winsock.addrinfoex">ADDRINFOEXW</a> structure that provides hints about the type of socket
     that the caller supports.
     </p>
<p>The <a href="winsock.addrinfoex">ADDRINFOEXW</a> structure is defined in the 
     Ws2def.h header. It is identical to the  
     <a href="winsock.addrinfoex">addrinfoex</a> structure.</p>
<div class="alert"><b>Important</b>  The 
     Ws2def.h header file is automatically included in 
     Wsk.h. Do not use 
     Ws2def.h directly.</div>
<div> </div>
</dd>

### -param Result [out]

<dd>
<p>[out] A pointer to a caller-allocated buffer that receives a linked list of one or more
     <a href="winsock.addrinfoex">ADDRINFOEXW</a> structures that represent response information about the host.
     </p>
<div class="alert"><b>Note</b>  The caller must call the 
     <a href="..\wsk\nc-wsk-pfn-wsk-free-address-info.md">WskFreeAddressInfo</a> function to free
     this pointer.</div>
<div> </div>
<p>The <a href="winsock.addrinfoex">ADDRINFOEXW</a> structure is defined in the 
     Ws2def.h header. It is identical to the 
     <a href="winsock.addrinfoex">addrinfoex</a> structure.</p>
<div class="alert"><b>Important</b>  The 
     Ws2def.h header file is automatically included in 
     Wsk.h. Do not use 
     Ws2def.h directly.</div>
<div> </div>
</dd>

### -param OwningProcess [in, optional]

<dd>
<p>[in] An optional pointer to the process from which the function retrieves the security context.
     This security context indicates the user account context in which the function processes the name
     resolution request.
     </p>
<p>If this parameter is <b>NULL</b>, the function processes the name resolution request in the context of a
     predefined local account with minimal privileges.</p>
<p>If this parameter is not <b>NULL</b> and an impersonation token is in effect for the calling thread, this
     function fails and returns STATUS_INVALID_PARAMETER.</p>
</dd>

### -param OwningThread [in, optional]

<dd>
<p>[in] An optional pointer to the thread from which the function retrieves the security context.
     This parameter can be non-<b>NULL</b> only if 
     <i>OwningProcess</i> is non-<b>NULL</b>. Otherwise, this function fails and returns STATUS_INVALID_PARAMETER.
     </p>
<p>If this parameter is not <b>NULL</b> and an impersonation token is in effect for the calling thread, this
     function fails and returns STATUS_INVALID_PARAMETER.</p>
</dd>

### -param Irp [in, out]

<dd>
<p>[in/out] A pointer to an I/O request packet (IRP) to use to complete the request asynchronously.
     Upon completion of the request, 
     <i>Irp</i> -&gt;
     <b>Iostatus.Information</b> will hold the returned status code.</p>
</dd>
</dl>

## -returns
<p><b>WskGetAddressInfo</b> returns one of the following NTSTATUS codes:</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>An invalid parameter was specified.</p><dl>
<dt><b>STATUS_NO_MATCH</b></dt>
</dl><p>The host name cannot be resolved.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The function completed successfully. If the WSK application specified a pointer to an IRP in the
       
       <i>Irp</i> parameter, the IRP will be completed with a success status.</p><dl>
<dt><b>STATUS_PENDING</b></dt>
</dl><p>The WSK subsystem could not complete the function immediately. The WSK subsystem will complete
       the IRP after it has completed the control operation. The status of the control operation will be
       returned in the 
       <b>IoStatus.Status</b> field of the IRP.</p><dl>
<dt><b>Other status codes</b></dt>
</dl><p>An error occurred. The IRP will be completed with failure status.</p>

<p> </p>

## -remarks
<p>The process to which the 
    <i>OwningProcess</i> parameter points, or the thread to which the 
    <i>OwningThread</i> process points, indicates the security context for this function. The user account
    that is indicated by the security context indicates the context for the function's name resolution
    request.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7 and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a>
</dt>
<dt>
<a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-free-address-info.md">WskFreeAddressInfo</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_GET_ADDRESS_INFO callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
