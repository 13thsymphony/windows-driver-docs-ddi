---
UID: NS.NTDDNDIS._NDIS_RECEIVE_QUEUE_PARAMETERS
title: _NDIS_RECEIVE_QUEUE_PARAMETERS
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_PARAMETERS structure contains the configuration parameters of a receive queue.
old-location: netvista\ndis_receive_queue_parameters.htm
old-project: netvista
ms.assetid: fba87554-766d-45e2-8257-584ee78dd873
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_RECEIVE_QUEUE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_PARAMETERS, NDIS_RECEIVE_QUEUE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_RECEIVE_QUEUE_PARAMETERS
req.alt-loc: Ntddndis.h
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
---

# _NDIS_RECEIVE_QUEUE_PARAMETERS structure



## -description
The <b>NDIS_RECEIVE_QUEUE_PARAMETERS</b> structure contains the configuration parameters of a receive
  queue.



## -syntax

````
typedef struct _NDIS_RECEIVE_QUEUE_PARAMETERS {
  NDIS_OBJECT_HEADER          Header;
  ULONG                       Flags;
  NDIS_RECEIVE_QUEUE_TYPE     QueueType;
  NDIS_RECEIVE_QUEUE_ID       QueueId;
  NDIS_RECEIVE_QUEUE_GROUP_ID QueueGroupId;
  GROUP_AFFINITY              ProcessorAffinity;
  ULONG                       NumSuggestedReceiveBuffers;
  ULONG                       MSIXTableEntry;
  ULONG                       LookaheadSize;
  NDIS_VM_NAME                VmName;
  NDIS_QUEUE_NAME             QueueName;
#if (NDIS_SUPPORT_NDIS630)
  ULONG                       PortId;
  ULONG                       InterruptCoalescingDomainId;
#endif 
} NDIS_RECEIVE_QUEUE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_PARAMETERS;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_RECEIVE_QUEUE_PARAMETERS</b> structure. This member is formatted as an <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_CAPABILITIES</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to one of the following values: 




### -field NDIS_RECEIVE_QUEUE_PARAMETERS_REVISION_2

Added additional members for NDIS 6.30.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_PARAMETERS_REVISION_2</b>.


### -field NDIS_RECEIVE_QUEUE_PARAMETERS_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_PARAMETERS_REVISION_1</b>.

</dd>
</dl>

### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of the following flags. The following flags are valid for the 
     <a href="netvista.oid_receive_filter_allocate_queue">
     OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a> OID and the 
     <a href="netvista.oid_receive_filter_queue_parameters">
     OID_RECEIVE_FILTER_QUEUE_PARAMETERS</a> set and query OID:




### -field NDIS_RECEIVE_QUEUE_PARAMETERS_PER_QUEUE_RECEIVE_INDICATION

The miniport driver must not mix network packets for other receive queues with the packets for
       this queue in a single call to the 
       <a href="netvista.ndismindicatereceivenetbufferlists">
       NdisMIndicateReceiveNetBufferLists</a> function.


### -field NDIS_RECEIVE_QUEUE_PARAMETERS_LOOKAHEAD_SPLIT_REQUIRED

The network adapter must split a received packet at an offset equal to or greater than the
       requested lookahead size and use DMA to transfer the lookahead data and the post-lookahead data to
       separate shared memory segments.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, splitting packet data into separate lookahead buffers is no longer supported. Miniport drivers that support NDIS 6.30 or later versions must ignore this flag.</div>
<div> </div>
</dd>
</dl>
The following flags are valid for the 
     <a href="netvista.oid_receive_filter_queue_parameters">
     OID_RECEIVE_FILTER_QUEUE_PARAMETERS</a> set OID and <a href="https://msdn.microsoft.com/library/windows/hardware/hh439820">NDIS_STATUS_RECEIVE_FILTER_QUEUE_PARAMETERS</a> status indication:




### -field NDIS_RECEIVE_QUEUE_PARAMETERS_FLAGS_CHANGED

The setting in the 
       <b>Flags</b> member changed.


### -field NDIS_RECEIVE_QUEUE_PARAMETERS_PROCESSOR_AFFINITY_CHANGED

The setting in the 
       <b>ProcessorAffinity</b> member changed.


### -field NDIS_RECEIVE_QUEUE_PARAMETERS_SUGGESTED_RECV_BUFFER_NUMBERS_CHANGED

The setting in the 
       <b>NumSuggestedReceiveBuffers</b> member changed.


### -field NDIS_RECEIVE_QUEUE_PARAMETERS_NAME_CHANGED

The setting in the 
       <b>QueueName</b> member changed.

</dd>
</dl>
<div class="alert"><b>Note</b>  A driver determines which receive queue parameters have been changed by executing a bitwise <b>AND</b> operation between the <b>NDIS_RECEIVE_QUEUE_PARAMETERS_CHANGE_MASK</b> definition and the value in the <b>Flags</b> member. If the result is zero, no receive queue parameters have been changed.</div>
<div> </div>

### -field QueueType

An 
     <a href="netvista.ndis_receive_queue_type">NDIS_RECEIVE_QUEUE_TYPE</a> enumeration
     value that specifies the type of the receive queue.


### -field QueueId

An <b>NDIS_RECEIVE_QUEUE_ID</b> type value that contains a receive queue identifier. This identifier is an integer value between zero and the number of queues that the network adapter supports. A value of <b>NDIS_DEFAULT_RECEIVE_QUEUE_ID</b> specifies the default receive queue.


### -field QueueGroupId

This member is reserved for NDIS.


### -field ProcessorAffinity

A <b>GROUP_AFFINITY</b> value that specifies the group number and a bitmap of the CPUs that this queue
     can be associated with. At least one processor must be specified. Therefore, the value must not be
     zero.


### -field NumSuggestedReceiveBuffers

A <b>ULONG</b> value that contains a suggested value for the number of receive buffers that the network adapter should use to support the queue. This number can be adjusted relative to the resources that the
     miniport driver has available or in proportion to the number that the network adapter uses for other
     queues. For example, the actual number of receive buffers can be double or half of this suggested
     value.


### -field MSIXTableEntry

This member is reserved for NDIS.


### -field LookaheadSize

A <b>ULONG</b> value for the size, in bytes, of the lookahead size requirement for this queue. A network adapter that supports lookahead in VM queues splits a received packet at an offset equal to or greater
     than the requested lookahead size and uses DMA to transfer the lookahead data and the post-lookahead
     data to separate shared memory segments. If the 
     <b>LookaheadSize</b> is zero, the miniport driver must not split the packet.
     

<b>LookaheadSize</b> is valid when NDIS sets the
     <b>NDIS_RECEIVE_QUEUE_PARAMETERS_LOOKAHEAD_SPLIT_REQUIRED</b> flag in the <b>Flags</b> member. That is, the miniport driver must split
     the packet at the specified lookahead size if the flag is also set. If the flag is clear, a nonzero
     value for 
     <b>LookaheadSize</b> is invalid.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, splitting packet data into separate lookahead buffers is no longer supported. The value of this member must be zero.</div>
<div> </div>

### -field VmName

An <b>NDIS_VM_NAME</b> value that contains the description of the virtual machine that users read.


### -field QueueName

An <b>NDIS_QUEUE_NAME</b> value that contains the description of the queue that users read.


### -field PortId

A ULONG value that contains the unique identifier of a port on the Hyper-V extensible switch to which the VM queue is attached.




### -field InterruptCoalescingDomainId

This member is reserved for NDIS.


## -remarks
The <b>NDIS_RECEIVE_QUEUE_PARAMETERS</b> structure is used in the 
    <a href="netvista.oid_receive_filter_allocate_queue">
    OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a> OID and the 
    <a href="netvista.oid_receive_filter_queue_parameters">
    OID_RECEIVE_FILTER_QUEUE_PARAMETERS</a> OID.

In NDIS 6.30, the <b>NDIS_RECEIVE_QUEUE_PARAMETERS</b> structure is also used in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439820">NDIS_STATUS_RECEIVE_FILTER_QUEUE_PARAMETERS</a> status indications.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.20 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>
</dt>
<dt>
<a href="netvista.oid_receive_filter_allocate_queue">
   OID_RECEIVE_FILTER_ALLOCATE_QUEUE</a>
</dt>
<dt>
<a href="netvista.oid_receive_filter_queue_parameters">
   OID_RECEIVE_FILTER_QUEUE_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_receive_queue_type">NDIS_RECEIVE_QUEUE_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439820">NDIS_STATUS_RECEIVE_FILTER_QUEUE_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_QUEUE_PARAMETERS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

