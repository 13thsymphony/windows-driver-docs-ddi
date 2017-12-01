---
UID: NE.ntddk._WHEA_ERROR_PACKET_DATA_FORMAT
title: WHEA_ERROR_PACKET_DATA_FORMAT
author: windows-driver-content
description: The WHEA_ERROR_PACKET_DATA_FORMAT enumeration defines the raw hardware error data format in a hardware error packet.
old-location: whea\whea_error_packet_data_format.htm
old-project: whea
ms.assetid: 612fbfb7-2f10-45e8-8f99-1aba8fe79a5a
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: FILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_ERROR_PACKET_DATA_FORMAT
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
req.irql: 
req.iface: 
---

# WHEA_ERROR_PACKET_DATA_FORMAT enumeration



## -description
<p>The WHEA_ERROR_PACKET_DATA_FORMAT enumeration defines the raw hardware error data format in a hardware error packet.</p>


## -syntax

````
typedef enum _WHEA_ERROR_PACKET_DATA_FORMAT { 
  WheaDataFormatIPFSalRecord  = 0,
  WheaDataFormatXPFMCA,
  WheaDataFormatMemory,
  WheaDataFormatPCIExpress,
  WheaDataFormatNMIPort,
  WheaDataFormatPCIXBus,
  WheaDataFormatPCIXDevice,
  WheaDataFormatGeneric,
  WheaDataFormatMax
} WHEA_ERROR_PACKET_DATA_FORMAT, *PWHEA_ERROR_PACKET_DATA_FORMAT;
````


## -enum-fields
<dl>

### -field <a id="WheaDataFormatIPFSalRecord"></a><a id="wheadataformatipfsalrecord"></a><a id="WHEADATAFORMATIPFSALRECORD"></a><b>WheaDataFormatIPFSalRecord</b>

<dd>
<p>The raw data in the hardware error packet contains an Itanium processor family system abstraction layer (SAL) error record. For more information about the format of a SAL error record, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=72212">Intel Itanium Processor Family System Abstraction Layer Specification</a>.</p>
</dd>

### -field <a id="WheaDataFormatXPFMCA"></a><a id="wheadataformatxpfmca"></a><a id="WHEADATAFORMATXPFMCA"></a><b>WheaDataFormatXPFMCA</b>

<dd>
<p>The raw data in the hardware error packet is formatted as an MCA_EXCEPTION structure. For more information about the MCA_EXCEPTION structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540659">HalQuerySystemInformation</a>.</p>
</dd>

### -field <a id="WheaDataFormatMemory"></a><a id="wheadataformatmemory"></a><a id="WHEADATAFORMATMEMORY"></a><b>WheaDataFormatMemory</b>

<dd>
<p>The raw data in the hardware error packet contains memory error data. The format of this error data is dependent on the memory architecture.</p>
</dd>

### -field <a id="WheaDataFormatPCIExpress"></a><a id="wheadataformatpciexpress"></a><a id="WHEADATAFORMATPCIEXPRESS"></a><b>WheaDataFormatPCIExpress</b>

<dd>
<p>The raw data in the hardware error packet is formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a> structure.</p>
</dd>

### -field <a id="WheaDataFormatNMIPort"></a><a id="wheadataformatnmiport"></a><a id="WHEADATAFORMATNMIPORT"></a><b>WheaDataFormatNMIPort</b>

<dd>
<p>The raw data in the hardware error packet contains the data that was read from the nonmaskable interrupt (NMI) I/O ports by the NMI low-level hardware error handler (LLHEH). The format of this error data is specific to the implementation.</p>
</dd>

### -field <a id="WheaDataFormatPCIXBus"></a><a id="wheadataformatpcixbus"></a><a id="WHEADATAFORMATPCIXBUS"></a><b>WheaDataFormatPCIXBus</b>

<dd>
<p>The raw data in the hardware error packet contains PCI/PCI-X bus error data. The format of this error data is specific to the implementation.</p>
</dd>

### -field <a id="WheaDataFormatPCIXDevice"></a><a id="wheadataformatpcixdevice"></a><a id="WHEADATAFORMATPCIXDEVICE"></a><b>WheaDataFormatPCIXDevice</b>

<dd>
<p>The raw data in the hardware error packet contains a PCI/PCI-X device error data. The format of this error data is specific to the implementation.</p>
</dd>

### -field <a id="WheaDataFormatGeneric"></a><a id="wheadataformatgeneric"></a><a id="WHEADATAFORMATGENERIC"></a><b>WheaDataFormatGeneric</b>

<dd>
<p>The raw data in the hardware error packet is formatted as a <a href="..\ntddk\ns-ntddk--whea-generic-error.md">WHEA_GENERIC_ERROR</a> structure.</p>
</dd>

### -field <a id="WheaDataFormatMax"></a><a id="wheadataformatmax"></a><a id="WHEADATAFORMATMAX"></a><b>WheaDataFormatMax</b>

<dd>
<p>The maximum number of formats of raw hardware error data.</p>
</dd>
</dl>

## -remarks
<p>The <a href="..\ntddk\ns-ntddk--whea-error-packet-v2.md">WHEA_ERROR_PACKET_V2</a> structure contains a member of type WHEA_ERROR_PACKET_DATA_FORMAT that specifies the format of the raw data that is contained in the hardware error packet.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows 7 and later versions of Windows.
</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-packet-v2.md">WHEA_ERROR_PACKET_V2</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-generic-error.md">WHEA_GENERIC_ERROR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_PACKET_DATA_FORMAT enumeration%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
