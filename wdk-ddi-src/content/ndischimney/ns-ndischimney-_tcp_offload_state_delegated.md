---
UID: NS.NDISCHIMNEY._TCP_OFFLOAD_STATE_DELEGATED
title: _TCP_OFFLOAD_STATE_DELEGATED
author: windows-driver-content
description: The TCP_OFFLOAD_STATE_DELEGATED structure contains the delegated variables of a TCP connection state object.
old-location: netvista\tcp_offload_state_delegated.htm
old-project: netvista
ms.assetid: ab16cfa1-24f6-434a-a687-07e19172f185
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _TCP_OFFLOAD_STATE_DELEGATED, TCP_OFFLOAD_STATE_DELEGATED, *PTCP_OFFLOAD_STATE_DELEGATED
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
req.alt-api: TCP_OFFLOAD_STATE_DELEGATED
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

# _TCP_OFFLOAD_STATE_DELEGATED structure



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]
The TCP_OFFLOAD_STATE_DELEGATED structure contains the delegated variables of a TCP connection state
  object.


## -syntax

````
typedef struct _TCP_OFFLOAD_STATE_DELEGATED {
  OFFLOAD_STATE_HEADER         Header;
  TCP_OFFLOAD_CONNECTION_STATE State;
  USHORT                       Flags;
  ULONG                        RcvNxt;
  ULONG                        RcvWnd;
  ULONG                        SndUna;
  ULONG                        SndNxt;
  ULONG                        SndMax;
  ULONG                        SndWnd;
  ULONG                        MaxSndWnd;
  ULONG                        SendWL1;
  ULONG                        CWnd;
  ULONG                        SsThresh;
  USHORT                       SRtt;
  USHORT                       RttVar;
  ULONG                        TsRecent;
  ULONG                        TsRecentAge;
  ULONG                        TsTime;
  ULONG                        TotalRT;
  UCHAR                        DupAckCount;
  UCHAR                        SndWndProbeCount;
  struct {
    UCHAR ProbeCount;
    ULONG TimeoutDelta;
  } KeepAlive;
  struct {
    UCHAR Count;
    ULONG TimeoutDelta;
  } Retransmit;
  union {
    struct {
      PNET_BUFFER_LIST SendDataHead;
      PNET_BUFFER_LIST SendDataTail;
    };
    ULONG  SendBacklogSize;
  };
  union {
    PNET_BUFFER_LIST BufferedData;
    ULONG            ReceiveBacklogSize;
  };
} TCP_OFFLOAD_STATE_DELEGATED, *PTCP_OFFLOAD_STATE_DELEGATED;
````


## -struct-fields

### -field Header

An 
     <a href="netvista.offload_state_header">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the TCP_OFFLOAD_STATE_DELEGATED structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.

### -field State

The current state of the TCP connection (see RFC 793) as one of the following
     TCP_OFFLOAD_CONNECTION_STATE values:
     


### -field TcpConnectionClosed

No connection state.

### -field TcpConnectionListen

Waiting for a connection request from any remote TCP and port.

### -field TcpConnectionSynSent

Waiting for a matching connection request after having sent a connection request.

### -field TcpConnectionSynRcvd

Waiting for a confirming connection request acknowledgment after having both received and sent a
       connection request.

### -field TcpConnectionEstablished

An open connection: data received can be delivered to the user. The normal state for the data
       transfer phase of the connection.

### -field TcpConnectionFinWait1

Waiting for a connection termination request from the remote TCP, or an acknowledgment of the
       connection termination request that was previously sent.

### -field TcpConnectionFinWait2

Waiting for a connection termination request from the remote TCP.

### -field TcpConnectionCloseWait

Waiting for a connection termination request from the local user.

### -field TcpConnectionClosing

Waiting for a connection termination request acknowledgment from the remote TCP.

### -field TcpConnectionLastAck

Waiting for an acknowledgment of the connection termination request previously sent to the
       remote TCP, which includes an acknowledgment of its connection termination request.

### -field TcpConnectionTimeWait

Waiting for enough time to pass to ensure that the remote TCP received the acknowledgment of its
       connection termination request.
</dd>
</dl>
 Note that the host stack can offload a TCP connection when the connection is in any state
     except 
     <b>TcpConnectionClosed</b>, 
     <b>TcpConnectionListen</b>, 
     <b>TcpConnectionSynRcvd</b>, 
     
<b>TcpConnectionSynSent</b>, or 
     <b>TcpConnectionTimeWait</b> state. The host stack can query, update, invalidate, or terminate a TCP
     connection regardless of the connection state.

### -field Flags

Reserved for system use.

### -field RcvNxt

The sequence number for the next receive segment (see RCV.NEXT in RFC 793).

### -field RcvWnd

The receive window size, in bytes (see RCV.WND in RFC 793).

### -field SndUna

The sequence number for the first byte of unacknowledged data (see SND.UNA in RFC 793). For more information, see <a href="netvista.send_data_that_contains_data_to_be_retransmitted">Send Data That Contains Data to Be Retransmitted</a>.

### -field SndNxt

The sequence number for the next byte to send on the connection (see SND.NXT in RFC 793). For more information, see <a href="netvista.send_data_that_contains_data_to_be_retransmitted">Send Data That Contains Data to Be Retransmitted</a>.

### -field SndMax

The maximum sequence number that has been sent on the connection. For more information, see <a href="netvista.send_data_that_contains_data_to_be_retransmitted">Send Data That Contains Data to Be Retransmitted</a>.

### -field SndWnd

The send window size, in bytes (see SND.WND in RFC 793).

### -field MaxSndWnd

The maximum send window size, in bytes (see RFC 813).

### -field SendWL1

The segment sequence number used for the last window update (see SND.WL1 in RFC 793).

### -field CWnd

The congestion window size, in bytes (see cwnd in RFC 2581).

### -field SsThresh

The slow start threshold, in bytes (see ssthresh in RFC 2581).

### -field SRtt

The smoothed round-trip time, in clock ticks (see SRTT in RFCs 793 and 2988). Maintained on a per
     connection basis because it takes into account path, host, and sometimes application behavior.

### -field RttVar

The round trip time variation, in clock ticks (see RTTVAR in RFC 2988).

### -field TsRecent

The timestamp value to send in the next ACK (see TS.Recent in RFC 1323)

### -field TsRecentAge

The length of time, in clock ticks, since the most recent timestamp was received (see RFC
     1323).

### -field TsTime

The current value of the adjusted timestamp.

### -field TotalRT

The total time, in clock ticks, that has been spent retransmitting the current TCP segment.

### -field DupAckCount

The number of ACKs that have been accepted for the same sequence number (see RFC 1323).

### -field SndWndProbeCount

The current send window probe round. For a description of the send window probe round, see 
     <a href="netvista.persist_timer">Persist Timer</a>.

### -field KeepAlive

This member is a union that consists of the following members:

### -field ProbeCount

The number of keepalive probes that have been sent that have not received a response (see RFC
      1122).

### -field TimeoutDelta

The time remaining, in clock ticks, until the next keepalive timeout (see RFC 1122). Note that a
      value of -1 immediately after the TCP connection was offloaded indicates that the keepalive timer was
      not running when the connection was offloaded. If the offload target's keepalive timer is not running,
      the offload target should return -1 in this member when responding to a call to the
      MiniportQueryOffload function or the MiniportTerminateOffload function.
</dd>
</dl>

### -field Retransmit

This member is a union that consists of the following members:

### -field Count

The number of retransmits that have been sent (see RFC 2581).

### -field TimeoutDelta

The time, in clock ticks, remaining until the next retransmit timeout (see RFC 2581). Note that a
      value of -1 immediately after the TCP connection was offloaded indicates that the retransmit timer was
      not running when the connection was offloaded. The retransmit timer was not running because there was
      no outstanding send data on the connection when the connection was offloaded. If the offload target's
      retransmit timer is not running, the offload target should return -1 in this member when responding to
      a call to the MiniportQueryOffload function or the MiniportTerminateOffload function.
</dd>
</dl>

### -field SendDataHead

A pointer to a 
       <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure. This
       NET_BUFFER_LIST structure is in the linked list that is pointed to by the 
       <b>NetBufferListChain</b> member of the 
       <a href="netvista.ndis_miniport_offload_block_list">
       NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that immediately precedes the
       TCP_OFFLOAD_STATE_DELEGATED structure. If the 
       <b>NetBufferListChain</b> pointer is <b>NULL</b>, 
       <b>SendDataHead</b> is not significant.
       
The 
       <b>SendDataHead</b> pointer points to the first NET_BUFFER_LIST structure whose NET_BUFFER structure
       has buffered the send data associated with it.
This variable is used only in an initiate offload or terminate offload operation. For more
       information about how this variable is used, see 
       <a href="netvista.handling_outstanding_send_data_during_and_after_an_offload_operation">Handling Outstanding Send Data During and After an Offload Operation</a> and 
       <a href="netvista.handling_outstanding_send_data_during_a_terminate_offload_operation">Handling Outstanding Send Data During a Terminate Offload Operation</a>.

### -field SendDataTail

A pointer to a 
       <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure. This
       NET_BUFFER_LIST structure is in the linked list that is pointed to by the NetBufferListChain member of
       the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that immediately precedes the
       TCP_OFFLOAD_STATE_DELEGATED structure. If the NetBufferListChain pointer is <b>NULL</b>, SendDataTail is not
       significant.
       
The SendDataTail pointer points to the last NET_BUFFER_LIST structure whose NET_BUFFER structure
       has buffered the send data associated with it.
This variable is used only in an initiate offload or terminate offload operation. For more
       information about how this variable is used, see 
       <a href="netvista.handling_outstanding_send_data_during_and_after_an_offload_operation">Handling Outstanding Send Data During and After an Offload
       Operation</a> and 
       <a href="netvista.handling_outstanding_send_data_during_a_terminate_offload_operation">Handling Outstanding Send Data During a Terminate Offload
       Operation</a>


### -field SendBacklogSize

The offload target specifies this value to indicate the number of data bytes that the host stack
       should have outstanding at the offload target for optimum performance. (This is the number of send
       bytes that have been passed to the offload target but that have not yet been completed by the offload
       target.) The specific variables and algorithm that the offload target uses to calculate the send
       backlog size are implementation-specific. The send backlog size can be a function of the roundtrip
       time (RTT) for the connection, the interface bandwidth, and other parameters. An offload target could,
       for example, use the minimum of the bandwidth/delay product and the advertised received window. Note
       however, that the send backlog size does not vary according to the number of data bytes that are
       currently posted for transmission on the connection.
The host stack can query the TCP delegated state for the connection to obtain the send backlog
       size. In addition, the offload target can indicate a change in the send backlog size by calling the 
       <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">
       NdisTcpOffloadEventHandler</a> function.
If the offload target does not support the send-backlog-size feature, it must write a value of
       0xFFFFFFFF to 
       <b>SendBacklogSize</b> when the TCP-delegated state for the connection is queried. The 
       <b>SendBacklogSize</b> variable is not used in the terminate offload operation.

### -field BufferedData

A pointer to buffered receive data. The host stack can pass such data to the offload target when
      offloading a TCP connection. (For more information, see 
      <a href="netvista.handling_buffered_receive_data_during_and_after_an_offload_operation">Handling Buffered Receive Data During and After an Offload Operation</a>.) The
      offload target can pass such data to the host stack when uploading a TCP connection. (For more
      information, see 
      <a href="netvista.handling_buffered_receive_data_during_a_terminate_offload_operation">Handling Buffered Receive Data During a Terminate Offload Operation</a>.)

### -field ReceiveBacklogSize

The offload target specifies this value to indicate the number of receive data bytes that are
      buffered in the offload target for the offloaded TCP connection. The host stack can query the TCP
      delegated state for the connection to obtain this value. The host stack uses this value to post one or
      more receive requests on the connection that are large enough to hold all of the buffered data.
      
If the offload target does not support the receive backlog size feature, it should write a value of
      0xFFFFFFFF to 
      <b>ReceiveBacklogSize</b> .

## -remarks
The host stack provides initial values for the TCP delegated variables when it offloads these
    variables to the offload target. After it is offloaded, the TCP delegated variables are owned and
    maintained by the offload target. Only the offload target can change the value of an offloaded TCP
    delegated variable. The offload target does not notify the host stack of changes to the values of
    offloaded TCP delegated variables. However, the host stack can query the value of offloaded TCP delegated
    variables, which causes NDIS to call the offload target's 
    <a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a> function.
    When the host stack terminates the offload of the TCP connection state object by causing NDIS to call the
    offload target's 
    <a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">
    MiniportTerminateOffload</a> function, the offload target passes the value of the TCP delegated
    variables in the terminated TCP connection state object back to the host stack.

When passed to an offload target, a TCP_OFFLOAD_STATE_DELEGATED structure is associated with an 
    <a href="netvista.ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which contains a header that is formatted as an 
    <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure. The
    Revision member of the NDIS_OBJECT_HEADER structure, in this case, specifies the revision number of the
    TCP_OFFLOAD_STATE_DELEGATED structure.

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
<a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a>
</dt>
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
<a href="netvista.tcp_offload_state_const">TCP_OFFLOAD_STATE_CONST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_STATE_DELEGATED structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
