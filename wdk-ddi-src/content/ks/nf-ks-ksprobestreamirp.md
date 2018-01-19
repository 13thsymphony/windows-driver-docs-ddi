---
UID : NF:ks.KsProbeStreamIrp
title : KsProbeStreamIrp function
author : windows-driver-content
description : The KsProbeStreamIrp function makes the specified modifications to the input and output buffers of the given IRP based on the flags passed, and it then validates the stream header.
old-location : stream\ksprobestreamirp.htm
old-project : stream
ms.assetid : 25b49781-2676-4b5e-b17b-dcb1bf98b297
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsProbeStreamIrp
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsProbeStreamIrp
req.alt-loc : Ks.lib,Ks.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : 
req.typenames : 
---


# KsProbeStreamIrp function
The <b>KsProbeStreamIrp</b> function makes the specified modifications to the input and output buffers of the given IRP based on the flags passed, and it then validates the stream header. This is useful when localizing exception handling or performing asynchronous work on an IRP. The resulting IRP is in essentially the METHOD_OUT_DIRECT or METHOD_IN_DIRECT format, with the exception that the access to the data buffer may be <b>IoModifyAccess</b>, depending on the flags passed to this function or the flags in the stream header.

## Syntax

````
NTSTATUS KsProbeStreamIrp(
  _Inout_  PIRP  Irp,
  _In_     ULONG ProbeFlags,
  _In_opt_ ULONG HeaderSize
);
````

## Parameters

`Irp`

Specifies the IRP whose input and output buffers are to be mapped. The requester mode of the IRP is used when probing the buffers.

`ProbeFlags`

Specifies flags specifying how to probe the streaming IRP; the flags are listed in the following table.

`OPTIONAL`




## Return Value

The <b>KsProbeStreamIrp</b> function returns STATUS_SUCCESS if successful, or it returns a memory or access error.

## Remarks

If the function is used only to allocate MDL's and not to probe and lock the addresses, the caller must have a completion routine to clean up the MDL's. For instance, a just-in-time locking mechanism can allocate the MDL list but only lock memory as needed. The client must provide cleanup code to remove the partially locked MDL list before the IRP is completed, presumably in a completion routine.

If the headers appear to have already been copied to a system buffer, it is not validated again. In general, calling the <b>KsProbeStreamIrp</b> function multiple times with an IRP is not harmful. After calling the function, the stream headers are available in PIRP.AssociatedIrp.SystemBuffer. If the stream buffer MDLs have been allocated, they are available through the PIRP.MdlAddress. 

The following defines are used for the <i>ProbeFlags</i> variable: 

KSPROBE_READ

Indicates that the operation is a stream read on the device. This is the default.

KSPROBE_WRITE

Indicates that the operation is a stream write on the device.

KSPROBE_ALLOCATEMDL

Indicates that MDLs should be allocated for the stream buffers if they have not already been allocated. If no stream buffers are present, the flag is ignored. If KSPROBE_PROBEANDLOCK is not specified at the same time as this flag, the caller must have a completion routine in order to clean up any MDL's if not all the MDLs were successfully probed and locked.

KSPROBE_PROBEANDLOCK

If the KSPROBE_ALLOCATEMDL is set, indicates that the memory referenced by the MDLs for the stream buffers should be probed and locked. If the MDL allocation flag is not set, this flag is ignored even if the MDL allocation has previously taken place. The method of probing is determined by what type of IRP is being passed. For a write operation, <b>IoReadAccess</b> is used. For a read operation, <b>IoWriteAccess</b> is used. If the client that sent the data is using the nonpaged pooll, appropriate MDLs are initialized rather than probing and locking.

KSPROBE_SYSTEMADDRESS

Retrieves a system address for each MDL in the chain so the caller does not need to do this in a separate step. This is ignored if the probe and lock flag is not set, even if the MDLs have previously been probed.

KSPROBE_ALLOWFORMATCHANGE

For a Stream Write, allows the KSSTREAM_HEADER_OPTIONSF_TYPECHANGED flag to be set in the stream header. This implies that the stream header is not of extended length, even if an extended header size was indicated. Also, there may only be one stream header contained in the IRP in this case. The buffer associated with this header contains the new data format. For system memory data streams, the buffer should not have been acquired from the negotiated allocator, as it is not part of the data stream.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |