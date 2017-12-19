---
UID: NS.NDISCHIMNEY._TCP_OFFLOAD_STATE_CONST
title: _TCP_OFFLOAD_STATE_CONST
author: windows-driver-content
description: The TCP_OFFLOAD_STATE_CONST structure contains the constant variables of a TCP connection state object.
old-location: netvista\tcp_offload_state_const.htm
old-project: NetVista
ms.assetid: 3e80f963-a494-475a-a246-abe5674dbcb6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _TCP_OFFLOAD_STATE_CONST, TCP_OFFLOAD_STATE_CONST, PTCP_OFFLOAD_STATE_CONST, *PTCP_OFFLOAD_STATE_CONST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TCP_OFFLOAD_STATE_CONST
req.alt-loc: ndischimney.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _TCP_OFFLOAD_STATE_CONST structure



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The TCP_OFFLOAD_STATE_CONST structure contains the constant variables of a TCP connection state
  object.



## -syntax

````
typedef struct _TCP_OFFLOAD_STATE_CONST {
  OFFLOAD_STATE_HEADER Header;
  USHORT               Flags;
  USHORT               RemotePort;
  USHORT               LocalPort;
  UCHAR                SndWindScale  :4;
  UCHAR                RcvWindScale  :4;
  USHORT               RemoteMss;
  ULONG                HashValue;
} TCP_OFFLOAD_STATE_CONST, *PTCP_OFFLOAD_STATE_CONST;
````


## -struct-fields

### -field Header

An 
     <a href="netvista.offload_state_header">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the TCP_OFFLOAD_STATE_CONST structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.


### -field Flags

A bitmask that can be set to zero or any of the following flags, combined with bitwise OR:
     




### -field TCP_FLAG_TIMESTAMP_ENABLED

The host stack sets this flag to enable the TCP timestamp option on the connection. (For more
       information about the TCP timestamp option, see RFC 1323.) When this option is enabled, the offload
       target must place a timestamp in each TCP segment that it sends. The host stack clears this flag to
       disable the TCP timestamp option on the connection.


### -field TCP_FLAG_SACK_ENABLED

The host stack sets this flag to enable selective acknowledgments (SACKs) on the connection.
       (For more information about the SACKs, see RFC 2018.) When this option is enabled, the offload target
       sends and receives SACK blocks over the TCP connection. The host stack clears this flag to disable
       SACKs on the connection.


### -field TCP_FLAG_WINDOW_SCALING_ENABLED

The host stack sets this flag to cause the offload target to use scale factors (SndWindScale and
       RcvWindScale) to compute send and receive windows for the connection. (For more information about
       window scale factors, see RFCs 2883 and 3517.) The host stack clears this flag to disable this
       option.

</dd>
</dl>

### -field RemotePort

The destination port number (see RFC 793).


### -field LocalPort

The source port number (see RFC 793).


### -field SndWindScale

The send window scale factor (see RFC 1323).


### -field RcvWindScale

The receive window scale factor (see RFC 1323).


### -field RemoteMss

The initial maximum segment size (MSS) advertised by the remote endpoint during TCP connection
     setup. (For more information about MSS, see RFC 2581.)


### -field HashValue

A 32-bit hash value that the offload target uses for 
     <a href="netvista.receive_side_scaling_on_an_offloaded_tcp_connection">receive side
     scaling (RSS)</a> processing on the TCP connection if the offload target supports RSS.


## -remarks
The value of each TCP constant variable does not change during the life of a TCP connection. Neither
    the host stack nor the offload target changes the values of a TCP constant variable. When the host stack
    terminates the offload of the TCP connection state object by causing NDIS to call the offload target's 
    <a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">
    MiniportTerminateOffload</a> function, the offload target does not return the value of the offloaded
    TCP constant variables to the host stack.

When passed to an offload target, a TCP_OFFLOAD_STATE_CONST structure is associated with an 
    <a href="netvista.ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which contains a header that is formatted as an 
    <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure. The 
    <b>Revision</b> member of the NDIS_OBJECT_HEADER structure, in this case, specifies the revision number of
    the TCP_OFFLOAD_STATE_CONST structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.offload_state_header">OFFLOAD_STATE_HEADER</a>
</dt>
<dt>
<a href="netvista.tcp_offload_state_cached">TCP_OFFLOAD_STATE_CACHED</a>
</dt>
<dt>
<a href="netvista.tcp_offload_state_delegated">TCP_OFFLOAD_STATE_DELEGATED</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20TCP_OFFLOAD_STATE_CONST structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

