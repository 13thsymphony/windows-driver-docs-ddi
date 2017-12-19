---
UID: NS.NTDDK._WHEA_XPF_BUS_CHECK
title: _WHEA_XPF_BUS_CHECK
author: windows-driver-content
description: The WHEA_XPF_BUS_CHECK union describes bus error information for an x86 or x64 processor.
old-location: whea\whea_xpf_bus_check.htm
old-project: whea
ms.assetid: 7886a796-2755-4367-bbbd-2017e7900bf4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WHEA_XPF_BUS_CHECK, *PWHEA_XPF_BUS_CHECK, WHEA_XPF_BUS_CHECK, PWHEA_XPF_BUS_CHECK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_XPF_BUS_CHECK
req.alt-loc: ntddk.h
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

# _WHEA_XPF_BUS_CHECK structure



## -description
The WHEA_XPF_BUS_CHECK union describes bus error information for an x86 or x64 processor.



## -syntax

````
typedef union _WHEA_XPF_BUS_CHECK {
  struct {
    ULONGLONG TransactionTypeValid  :1;
    ULONGLONG OperationValid  :1;
    ULONGLONG LevelValid  :1;
    ULONGLONG ProcessorContextCorruptValid  :1;
    ULONGLONG UncorrectedValid  :1;
    ULONGLONG PreciseIPValid  :1;
    ULONGLONG RestartableIPValid  :1;
    ULONGLONG OverflowValid  :1;
    ULONGLONG ParticipationValid  :1;
    ULONGLONG TimeoutValid  :1;
    ULONGLONG AddressSpaceValid  :1;
    ULONGLONG ReservedValid  :5;
    ULONGLONG TransactionType  :2;
    ULONGLONG Operation  :4;
    ULONGLONG Level  :3;
    ULONGLONG ProcessorContextCorrupt  :1;
    ULONGLONG Uncorrected  :1;
    ULONGLONG PreciseIP  :1;
    ULONGLONG RestartableIP  :1;
    ULONGLONG Overflow  :1;
    ULONGLONG Participation  :2;
    ULONGLONG Timeout  :1;
    ULONGLONG AddressSpace  :2;
    ULONGLONG Reserved  :29;
  };
  ULONGLONG XpfBusCheck;
} WHEA_XPF_BUS_CHECK, *PWHEA_XPF_BUS_CHECK;
````


## -struct-fields

### -field TransactionTypeValid

A single bit that indicates that the <b>TransactionType</b> member contains valid data.


### -field OperationValid

A single bit that indicates that the <b>Operation</b> member contains valid data.


### -field LevelValid

A single bit that indicates that the <b>Level</b> member contains valid data.


### -field ProcessorContextCorruptValid

A single bit that indicates that the <b>ProcessorContextCorrupt</b> member contains valid data.


### -field UncorrectedValid

A single bit that indicates that the <b>Uncorrected </b>member contains valid data.


### -field PreciseIPValid

A single bit that indicates that the <b>PreciseIP</b> member contains valid data.


### -field RestartableIPValid

A single bit that indicates that the <b>RestartableIP</b> member contains valid data.


### -field OverflowValid

A single bit that indicates that the <b>Overflow</b> member contains valid data.


### -field ParticipationValid

A single bit that indicates that the <b>Participation</b> member contains valid data.


### -field TimeoutValid

A single bit that indicates that the <b>Timeout</b> member contains valid data.


### -field AddressSpaceValid

A single bit that indicates that the <b>AddressSpace</b> member contains valid data.


### -field ReservedValid

Reserved for system use.


### -field TransactionType

The type of transaction that was in progress when the error occurred. Possible values are:




### -field XPF_BUS_CHECK_TRANSACTIONTYPE_INSTRUCTION

A processor instruction transaction.


### -field XPF_BUS_CHECK_TRANSACTIONTYPE_DATAACCESS

A data access transaction.


### -field XPF_BUS_CHECK_TRANSACTIONTYPE_GENERIC

A generic transaction.

</dd>
</dl>
This member contains valid data only if the <b>TransactionTypeValid</b> bit is set.


### -field Operation

The type of bus operation that caused the error. Possible values are:




### -field XPF_BUS_CHECK_OPERATION_GENERIC

The type of operation cannot be determined.


### -field XPF_BUS_CHECK_OPERATION_GENREAD

A generic read operation.


### -field XPF_BUS_CHECK_OPERATION_GENWRITE

A generic write operation.


### -field XPF_BUS_CHECK_OPERATION_DATAREAD

A data read operation.


### -field XPF_BUS_CHECK_OPERATION_DATAWRITE

A data write operation.


### -field XPF_BUS_CHECK_OPERATION_INSTRUCTIONFETCH

An instruction fetch operation.


### -field XPF_BUS_CHECK_OPERATION_PREFETCH

An instruction prefetch operation.

</dd>
</dl>
This member contains valid data only if the <b>OperationValid</b> bit is set.


### -field Level

The level of the bus hierarchy where the error occurred.

This member contains valid data only if the <b>LevelValid</b> bit is set.


### -field ProcessorContextCorrupt

A single bit that indicates that the processor context might have been corrupted.

This member contains valid data only if the <b>ProcessorContextCorruptValid</b> bit is set.


### -field Uncorrected

A single bit that indicates that the error has not been corrected.

This member contains valid data only if the <b>UncorrectedValid</b> bit is set.


### -field PreciseIP

A single bit that indicates that the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="whea.whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> structure that contains this WHEA_XPF_BUS_CHECK union is directly associated with the error.

This member contains valid data only if the <b>PreciseIPValid</b> bit is set.


### -field RestartableIP

A single bit that indicates that program execution can be restarted reliably at the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="whea.whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> union that contains this WHEA_XPF_BUS_CHECK structure.

This member contains valid data only if the <b>RestartableIPValid</b> bit is set.


### -field Overflow

A single bit that indicates that an error overflow occurred.

This member contains valid data only if the <b>OverflowValid</b> bit is set.


### -field Participation

The type of participation by the local processor. Possible values are:




### -field XPF_BUS_CHECK_PARTICIPATION_PROCORIGINATED

The local processor originated the request.


### -field XPF_BUS_CHECK_PARTICIPATION_PROCRESPONDED

The local processor responded to the request.


### -field XPF_BUS_CHECK_PARTICIPATION_PROCOBSERVED

The local processor observed the request.


### -field XPF_BUS_CHECK_PARTICIPATION_GENERIC

A generic value for this member if none of the other values are applicable.

</dd>
</dl>
This member contains valid data only if the <b>ParticipationValid</b> bit is set.


### -field Timeout

A single bit that indicates that a timeout occurred.

This member contains valid data only if the <b>TimeoutValid</b> bit is set.


### -field AddressSpace

The type of address space that was associated with the transaction that caused the error. Possible values are:




### -field XPF_BUS_CHECK_ADDRESS_MEMORY

Memory address space.


### -field XPF_BUS_CHECK_ADDRESS_RESERVED

Reserved.


### -field XPF_BUS_CHECK_ADDRESS_IO

I/O address space.


### -field XPF_BUS_CHECK_ADDRESS_OTHER

An unclassified type of address space.

</dd>
</dl>
This member contains valid data only if the <b>AddressSpaceValid</b> bit is set.


### -field Reserved

Reserved for system use.


### -field XpfBusCheck

A ULONGLONG representation of the contents of the WHEA_XPF_BUS_CHECK union.


## -remarks
If the <b>CheckInfoId</b> member of a <a href="whea.whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> structure contains WHEA_BUSCHECK_GUID, the <b>CheckInfo</b> member of the WHEA_XPF_PROCINFO structure contains a WHEA_XPF_BUS_CHECK union.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.


</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="whea.whea_xpf_procinfo">WHEA_XPF_PROCINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_BUS_CHECK union%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

