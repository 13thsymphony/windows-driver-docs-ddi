---
UID: NS.fwpsk.FWPS_TRANSPORT_SEND_PARAMS0_
title: FWPS_TRANSPORT_SEND_PARAMS0_
author: windows-driver-content
description: The FWPS_TRANSPORT_SEND_PARAMS0 structure defines properties of an outbound transport layer packet.Note  FWPS_TRANSPORT_SEND_PARAMS0 is the specific version of FWPS_TRANSPORT_SEND_PARAMS used in Windows Vista and later.
old-location: netvista\fwps_transport_send_params0.htm
old-project: netvista
ms.assetid: 32320f33-2fa8-410b-9aa8-312c2e0da693
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FWPS_TRANSPORT_SEND_PARAMS0_, FWPS_TRANSPORT_SEND_PARAMS0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_TRANSPORT_SEND_PARAMS0
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# FWPS_TRANSPORT_SEND_PARAMS0_ structure



## -description
<p>The <b>FWPS_TRANSPORT_SEND_PARAMS0</b> structure defines properties of an outbound transport layer
  packet.</p>


## -syntax

````
typedef struct FWPS_TRANSPORT_SEND_PARAMS0_ {
  UCHAR      *remoteAddress;
  SCOPE_ID   remoteScopeId;
  WSACMSGHDR *controlData;
  ULONG      controlDataLength;
} FWPS_TRANSPORT_SEND_PARAMS0;
````


## -struct-fields
<dl>

### -field remoteAddress

<dd>
<p>A pointer to a buffer that specifies the remote IP address to which to send the socket. The remote
     address specified by this member can be different than the one passed as one of the incoming data values
     to the callout driver's 
     <a href="netvista.classifyfn">classifyFn</a> callout function.
     </p>
<p>The buffer can contain an IPv4 address (4 bytes) or an IPv6 address (16 bytes), and the address must
     be specified in network byte order. The IP version must match the 
     <i>AddressFamily</i> parameter specified in the 
     <a href="..\fwpsk\nf-fwpsk-fwpsinjecttransportsendasync0.md">
     FwpsInjectTransportSendAsync0</a> function.</p>
<p>The buffer must remain valid until the injection completion function is called.</p>
</dd>

### -field remoteScopeId

<dd>
<p>A <b>SCOPE_ID</b> structure that contains the scope identifier for the remote IP address. The scope
     identifier is provided to a callout through the 
     <b>remoteScopeId</b> member of the 
     <a href="netvista.fwps_incoming_metadata_values0">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="netvista.classifyfn">classifyFn</a> callout function. The <b>SCOPE_ID</b>
     structure is defined in 
     Ws2ipdef.h as follows.
     </p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct {
  union {
    struct {
      ULONG  Zone : 28;
      ULONG  Level : 4;
    };
    ULONG  Value;
  };
} SCOPE_ID, *PSCOPE_ID;</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field controlData

<dd>
<p>An optional pointer to a buffer that contains socket control data specified by the 
      <a href="winsock.wsasendmsg">WSASendMsg</a> function. For information about the <b>WSACMSGHDR</b> type, see 
      <a href="netvista.cmsghdr">CMSGHDR</a>.</p>
<p>If present, socket control data is provided to a callout with the 
      <b>controlData</b> member of the 
      <a href="netvista.fwps_incoming_metadata_values0">
      FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
      <a href="netvista.classifyfn">classifyFn</a> callout function.</p>
<p>If socket control data is not <b>NULL</b>, it must be deep-copied in the callout driver's implementation
      of the 
      <a href="netvista.classifyfn">classifyFn</a> function, and the <b>controlData</b> buffer must be kept valid
      until the injection completion function is called.</p>
</dd>

### -field controlDataLength

<dd>
<p>The length, in bytes, of the 
     <b>controlData</b> member.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows Vista.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.classifyfn">classifyFn</a>
</dt>
<dt>
<a href="netvista.cmsghdr">CMSGHDR</a>
</dt>
<dt>
<a href="netvista.fwps_incoming_metadata_values0">
   FWPS_INCOMING_METADATA_VALUES0</a>
</dt>
<dt>
<a href="netvista.fwps_transport_send_params1">FWPS_TRANSPORT_SEND_PARAMS1</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsinjecttransportsendasync0.md">
   FwpsInjectTransportSendAsync0</a>
</dt>
<dt>
<a href="winsock.wsasendmsg">WSASendMsg</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_TRANSPORT_SEND_PARAMS0 structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
