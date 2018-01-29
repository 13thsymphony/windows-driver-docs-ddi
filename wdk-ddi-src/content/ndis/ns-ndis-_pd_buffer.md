---
UID : NS:ndis._PD_BUFFER
title : _PD_BUFFER
author : windows-driver-content
description : This structure represents a PacketDirect (PD) packet, or a portion of a PD packet in a queue.
old-location : netvista\pd_buffer.htm
old-project : netvista
ms.assetid : 91555FBA-30F5-4CED-BA0D-2F0BE40BFF9E
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/PPD_BUFFER, netvista.pd_buffer, PD_BUFFER structure [Network Drivers Starting with Windows Vista], PPD_BUFFER structure pointer [Network Drivers Starting with Windows Vista], PD_BUFFER, ndis/PD_BUFFER, _PD_BUFFER, PPD_BUFFER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndis.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PD_BUFFER
---

# _PD_BUFFER structure
This structure represents a PacketDirect (PD) packet, or a portion of a PD packet in a queue.

## Syntax
````
typedef struct _PD_BUFFER {
  PD_BUFFER                                                       *NextPDBuffer;
  PD_BUFFER                                                       *NextPartialPDBuffer;
  PVOID                                                           PDClientReserved;
  _Field_size_bytes_(PDClientContextSize)  PVOID                  PDClientContext;
  _Field_size_bytes_(DataBufferSize)  
 PUCHAR                    DataBufferVirtualAddress;
   _Field_size_bytes_(DataBufferSize)  
      DMA_LOGICAL_ADDRESS DataBufferDmaLogicalAddress;
  ULONG                                                           DataBufferSize;
  USHORT                                                          PDClientContextSize;
  USHORT                                                          Attributes;
  USHORT                                                          Flags;
  USHORT                                                          DataStart;
  ULONG                                                           DataLength;
  union {
    struct {
      union {
        ULONG64 RxFilterContext;
        ULONG64 GftFlowEntryId;
      };
      ULONG                         RxHashValue;
      union {
        struct {
          ULONG RxIPHeaderChecksumSucceeded  :1;
          ULONG RxTCPChecksumSucceeded  :1;
          ULONG RxUDPChecksumSucceeded  :1;
          ULONG RxIPHeaderChecksumFailed  :1;
          ULONG RxTCPChecksumFailed  :1;
          ULONG RxUDPChecksumFailed  :1;
          ULONG RxHashComputed  :1;
          ULONG RxHashWithL4PortNumbers  :1;
          ULONG RxGftExceptionPacket  :1;
          ULONG RxGftCopyPacket  :1;
          ULONG RxGftSamplePacket  :1;
          ULONG RxReserved1  :5;
          ULONG RxCoalescedSegCount  :16;
          ULONG RxRscTcpTimestampDelta  :1;
        };
        ULONG  RxOffloads[2];
      };
      union {
        struct {
          ULONG TxIsIPv4  :1;
          ULONG TxIsIPv6  :1;
          ULONG TxTransportHeaderOffset  :10;
          ULONG TxMSS  :20;
          ULONG TxComputeIPHeaderChecksum  :1;
          ULONG TxComputeTCPChecksum  :1;
          ULONG TxComputeUDPChecksum  :1;
          ULONG TxIsEncapsulatedPacket  :1;
          ULONG TxInnerPacketOffsetsValid  :1;
          ULONG TxReserved1  :11;
          ULONG TxInnerFrameOffset  :8;
          ULONG TxInnerIpHeaderRelativeOffset  :6;
          ULONG TxInnerIsIPv6  :1;
          ULONG TxInnerTcpOptionsPresent  :1;
        };
        ULONG  TxOffloads[2];
      };
      PD_BUFFER_VIRTUAL_SUBNET_INFO VirtualSubnetInfo;
      PD_BUFFER_8021Q_INFO          Ieee8021qInfo;
      USHORT                        GftSourceVPortId;
      ULONG                         Reserved;
      UINT64                        ProviderScratch;
    } MetaDataV0;
  };
} PD_BUFFER, *PPD_BUFFER;
````

## Members


`_PD_BUFFER`



`Attributes`

The attributes must never be modified by the provider. The table below lists attributes that this <b>PD_BUFFER</b> structure can have.
<table>
<tr>
<th>Attribute</th>
<th>Description</th>
</tr>
<tr>
<td>PD_BUFFER_ATTR_BUILT_IN_DATA_BUFFER</td>
<td>A <b>PD_BUFFER</b> allocated with its own accompanying data buffer will have
this attribute set. The <b>PD_BUFFER</b> attributes must never be modified by clients
or providers.</td>
</tr>
</table>

`DataBufferDmaLogicalAddress`

This field represents the logical memory location used for storing the packet data. The provider
must use for DMA. The actual packet data is always at
    DataBufferDmaLogicalAddress+DataStart. The provider and the
    platform must never modify the value of this field after the <b>PD_BUFFER</b>
    initialization.

`DataBufferSize`

This is the total size of the allocated data buffer. The provider and the platform must never modify the value of this field
    after the <b>PD_BUFFER</b> initialization. This data type is <b>ULONG</b> instead of
    <b>USHORT</b> because of large send offload.

`DataBufferVirtualAddress`

This field represents the address that hosts and software can use to access/modify the packet contents. The actual packet data is always at  DataBufferVirtualAddress+DataStart. The provider and the      platform never modify the value of this field after the <b>PD_BUFFER</b>      initialization.

`DataLength`

The length of the this packet or partial packet data.

`DataStart`

This field denotes where the packet starts relative to the original starting address of the allocated data buffer. The provider must never modify this field. The provider adds this value to the
    DataBufferDmaLogicalAddress value to derive the actual
    target DMA address for packet reception/transmission. For example, the
    target DMA address value in the hardware receive/transmit descriptor
    must be set to DataBufferDmaLogicalAddress+DataStart when a <b>PD_BUFFER</b>
    is posted to a receive/transmit queue.

`Flags`

The following table lists flags that this <b>PD_BUFFER</b> structure can have.
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>PD_BUFFER_FLAG_PARTIAL_PACKET_HEAD</td>
<td>Indicates that this buffer is the head of partial packets.</td>
</tr>
</table>

`NextPartialPDBuffer`

A pointer to the next partial <b>PD_BUFFER</b> structure in the queue.

`NextPDBuffer`

A pointer to the next <b>PD_BUFFER</b> structure in the queue.

`PDClientContext`

The client and the provider are not allowed to modify this field.      If a client has allocated the <b>PD_BUFFER</b> with a non-zero value for      ClientContextSize, then the PDClientContext refers to a buffer size      of ClientContextSize. Otherwise, this field is NULL.

`PDClientContextSize`

When this value is non-zero, it is the size of the buffer pointed to by PDClientContext.
    The value of this field must only be modified by the platform. The platform does not change the value of this field after the <b>PD_BUFFER</b> allocation.

`PDClientReserved`

Reserved for system use. Do not use.

## Remarks
If an L2 packet is represented by multiple <b>PD_BUFFER</b> structures, the first <b>PD_BUFFER</b>
must have the PD_BUFFER_ATTR_BUILT_IN_DATA_BUFFER flag set and the
NextPartialPDBuffer field must point to the partial <b>PD_BUFFER</b> structures that
constitute the whole packet. Each of the partial <b>PD_BUFFER</b> structures must point to the next partial <b>PD_BUFFER</b> by using the NextPartialPDBuffer as opposed to the NextPDBuffer field. The NextPDBuffer field must be NULL in all partial <b>PD_BUFFER</b> structures except
for the head buffer. All partial PD_BUFFER structures except for the head buffer must
have the PD_BUFFER_ATTR_BUILT_IN_DATA_BUFFER flag cleared. The last partial
<b>PD_BUFFER</b> must have it's NextPartialPDBuffer field set to NULL. The total
length of the L2 packet is the sum of DataLength fields from each partial
<b>PD_BUFFER</b>. The head <b>PD_BUFFER</b> must contain up to and including the IP transport (TCP, UDP, SCTP, etc) header. In the case of encapsulation or double-encapsulation,
the inner-most IP transport header must be contained in the head <b>PD_BUFFER</b>.

When posting <b>PD_BUFFER</b> structures to receive queues, DataLength is ignored by
    the provider (For more information see the ReceiveDataLength description in the <a href="..\ndis\ns-ndis-_ndis_pd_queue_parameters.md">NDIS_PD_QUEUE_PARAMETERS</a> structure).
    When draining completed <b>PD_BUFFER</b>  structures from receive queues,
    the provider stores the length of the received packet in the  DataLength field. The length does not include FCS or any stripped 801Q
    headers.
    When posting <b>PD_BUFFER</b> structures to transmit queues, DataLength denotes the length
    of the packet to be sent. When draining completed <b>PD_BUFFER</b> structures from
    transmit queues, the provider leaves the DataLength field unmodified.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h |