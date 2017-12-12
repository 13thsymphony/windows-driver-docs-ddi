---
UID: NS.NTDDK._WHEA_MEMORY_ERROR_SECTION
title: _WHEA_MEMORY_ERROR_SECTION
author: windows-driver-content
description: The WHEA_MEMORY_ERROR_SECTION structure describes platform memory error data.
old-location: whea\whea_memory_error_section.htm
old-project: whea
ms.assetid: eede44f8-0e14-4256-9893-cbdb5ef4ef9b
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WHEA_MEMORY_ERROR_SECTION, *PWHEA_MEMORY_ERROR_SECTION, WHEA_MEMORY_ERROR_SECTION
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
req.alt-api: WHEA_MEMORY_ERROR_SECTION
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

# _WHEA_MEMORY_ERROR_SECTION structure



## -description
The WHEA_MEMORY_ERROR_SECTION structure describes platform memory error data.



## -syntax

````
typedef struct _WHEA_MEMORY_ERROR_SECTION {
  WHEA_MEMORY_ERROR_SECTION_VALIDBITS ValidBits;
  WHEA_ERROR_STATUS                   ErrorStatus;
  ULONGLONG                           PhysicalAddress;
  ULONGLONG                           PhysicalAddressMask;
  USHORT                              Node;
  USHORT                              Card;
  USHORT                              Module;
  USHORT                              Bank;
  USHORT                              Device;
  USHORT                              Row;
  USHORT                              Column;
  USHORT                              BitPosition;
  ULONGLONG                           RequesterId;
  ULONGLONG                           ResponderId;
  ULONGLONG                           TargetId;
  UCHAR                               ErrorType;
} WHEA_MEMORY_ERROR_SECTION, *PWHEA_MEMORY_ERROR_SECTION;
````


## -struct-fields

### -field ValidBits

A <a href="whea.whea_memory_error_section_validbits">WHEA_MEMORY_ERROR_SECTION_VALIDBITS</a> union that specifies which members of this structure contain valid data.


### -field ErrorStatus

A <a href="whea.whea_error_status">WHEA_ERROR_STATUS</a> structure that contains memory error status data.

This member contains valid data only if the <b>Validbits.ErrorStatus</b> bit is set.


### -field PhysicalAddress

The physical address where the memory error occurred.

This member contains valid data only if the <b>Validbits.PhysicalAddress</b> bit is set.


### -field PhysicalAddressMask

A bit mask that specifies which of the bits in the <b>PhysicalAddress</b> member contain valid address data.

This member contains valid data only if the <b>Validbits.PhysicalAddressMask</b> bit is set.


### -field Node

The identifier of the node that contains the memory where the memory error occurred in a system with multiple nodes.

This member contains valid data only if the <b>Validbits.Node</b> bit is set.


### -field Card

The card number of the card that contains the memory where the memory error occurred.

This member contains valid data only if the <b>Validbits.Card</b> bit is set.


### -field Module

The module number of the module that contains the memory where the memory error occurred.

This member contains valid data only if the <b>Validbits.Module</b> bit is set.


### -field Bank

The bank number of the memory bank that contains the memory where the memory error occurred.

This member contains valid data only if the <b>Validbits.Bank</b> bit is set.


### -field Device

The device number of the memory device that contains the memory where the memory error occurred.

This member contains valid data only if the <b>Validbits.Device</b> bit is set.


### -field Row

The row number of the location where the memory error occurred.

This member contains valid data only if the <b>Validbits.Row</b> bit is set.


### -field Column

The column number of the location where the memory error occurred.

This member contains valid data only if the <b>Validbits.Column</b> bit is set.


### -field BitPosition

The bit position where the memory error occurred.

This member contains valid data only if the <b>Validbits.BitPosition</b> bit is set.


### -field RequesterId

An identifier that uniquely identifies the requester associated with the error.

This member contains valid data only if the <b>Validbits.RequesterId</b> bit is set.


### -field ResponderId

An identifier that uniquely identifies the responder associated with the error.

This member contains valid data only if the <b>Validbits.ResponderId</b> bit is set.


### -field TargetId

The hardware address of the intended target of the transaction.

This member contains valid data only if the <b>Validbits.TargetId</b> bit is set.


### -field ErrorType

The type of memory error that occurred. Possible values are:




### -field WHEA_MEMERRTYPE_UNKNOWN

An unknown error.


### -field WHEA_MEMERRTYPE_NOERROR

No error occurred.


### -field WHEA_MEMERRTYPE_SINGLEBITECC

A single bit <a href="wdkgloss.e#wdkgloss.ecc#wdkgloss.ecc"><i>ECC</i></a> error.


### -field WHEA_MEMERRTYPE_MULTIBITECC

A multibit ECC error.


### -field WHEA_MEMERRTYPE_SINGLESYMCHIPKILL

A single symbol <a href="http://go.microsoft.com/fwlink/p/?linkid=81372">ChipKill</a> <a href="wdkgloss.e#wdkgloss.ecc#wdkgloss.ecc"><i>ECC</i></a> error.


### -field WHEA_MEMERRTYPE_MULTISYMCHIPKILL

A multiple symbol <a href="http://go.microsoft.com/fwlink/p/?linkid=81372">ChipKill</a> <a href="wdkgloss.e#wdkgloss.ecc#wdkgloss.ecc"><i>ECC</i></a> error.


### -field WHEA_MEMERRTYPE_MASTERABORT

A master abort.


### -field WHEA_MEMERRTYPE_TARGETABORT

A target abort.


### -field WHEA_MEMERRTYPE_PARITYERROR

A parity error.


### -field WHEA_MEMERRTYPE_WATCHDOGTIMEOUT

A watchdog timeout.


### -field WHEA_MEMERRTYPE_INVALIDADDRESS

An invalid memory address.


### -field WHEA_MEMERRTYPE_MIRRORBROKEN

A broken memory mirror.


### -field WHEA_MEMERRTYPE_MEMORYSPARING

A memory sparing error.

</dd>
</dl>
This member contains valid data only if the <b>Validbits.ErrorType</b> bit is set.


## -remarks
The WHEA_MEMORY_ERROR_SECTION structure describes the error data that is contained in a platform memory error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a platform memory error section only if the <b>SectionType </b>member of one of the <a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains MEMORY_ERROR_SECTION_GUID.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>
</dt>
<dt>
<a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
</dt>
<dt>
<a href="whea.whea_error_status">WHEA_ERROR_STATUS</a>
</dt>
<dt>
<a href="whea.whea_memory_error_section_validbits">WHEA_MEMORY_ERROR_SECTION_VALIDBITS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_MEMORY_ERROR_SECTION structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

