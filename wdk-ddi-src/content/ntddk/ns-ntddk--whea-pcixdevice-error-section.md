---
UID: NS.ntddk._WHEA_PCIXDEVICE_ERROR_SECTION
title: WHEA_PCIXDEVICE_ERROR_SECTION
author: windows-driver-content
description: The WHEA_PCIXDEVICE_ERROR_SECTION structure describes PCI or PCI-X device error data.
old-location: whea\whea_pcixdevice_error_section.htm
old-project: whea
ms.assetid: 0d2ec4e5-193d-45bf-8588-6afc1a9fb68c
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_PCIXDEVICE_ERROR_SECTION, WHEA_PCIXDEVICE_ERROR_SECTION, *PWHEA_PCIXDEVICE_ERROR_SECTION
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
req.alt-api: WHEA_PCIXDEVICE_ERROR_SECTION
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
req.iface: 
---

# WHEA_PCIXDEVICE_ERROR_SECTION structure



## -description
<p>The WHEA_PCIXDEVICE_ERROR_SECTION structure describes PCI or PCI-X device error data.</p>


## -syntax

````
typedef struct _WHEA_PCIXDEVICE_ERROR_SECTION {
  WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS ValidBits;
  WHEA_ERROR_STATUS                       ErrorStatus;
  WHEA_PCIXDEVICE_ID                      IdInfo;
  ULONG                                   MemoryNumber;
  ULONG                                   IoNumber;
  WHEA_PCIXDEVICE_REGISTER_PAIR           RegisterDataPairs[ANYSIZE_ARRAY];
} WHEA_PCIXDEVICE_ERROR_SECTION, *PWHEA_PCIXDEVICE_ERROR_SECTION;
````


## -struct-fields
<dl>

### -field ValidBits

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-pcixdevice-error-section-validbits.md">WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS</a> union that specifies which members of this structure contain valid data.</p>
</dd>

### -field ErrorStatus

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-error-status.md">WHEA_ERROR_STATUS</a> structure that contains PCI or PCI-X device error status data.</p>
<p>This member contains valid data only if the <b>ValidBits.ErrorStatus</b> bit is set.</p>
</dd>

### -field IdInfo

<dd>
<p>A WHEA_PCIXDEVICE_ID structure that contains data that identifies the PCI or PCI-X device. The WHEA_PCIXDEVICE_ID structure is defined as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _WHEA_PCIXDEVICE_ID {
  USHORT  VendorId;
  USHORT  DeviceId;
  ULONG  ClassCode:24;
  ULONG  FunctionNumber:8;
  ULONG  DeviceNumber:8;
  ULONG  BusNumber:8;
  ULONG  SegmentNumber:8;
  ULONG  Reserved1:8;
  ULONG  Reserved2;
} WHEA_PCIXDEVICE_ID, *PWHEA_PCIXDEVICE_ID;</pre>
</td>
</tr>
</table></span></div>
<p></p>
<dl>

### -field VendorId

<dd>
<p>The vendor ID of the device.</p>
</dd>

### -field DeviceId

<dd>
<p>The device ID of the device.</p>
</dd>

### -field ClassCode

<dd>
<p>The class code of the device.</p>
</dd>

### -field FunctionNumber

<dd>
<p>The function number of the device on the bus.</p>
</dd>

### -field DeviceNumber

<dd>
<p>The device number of the device on the bus.</p>
</dd>

### -field BusNumber

<dd>
<p>The number of the bus that contains the device.</p>
</dd>

### -field SegmentNumber

<dd>
<p>The number of the bus segment that contains the device.</p>
</dd>

### -field Reserved1

<dd>
<p>Reserved for system use.</p>
</dd>

### -field Reserved2

<dd>
<p>Reserved for system use.</p>
</dd>
</dl>
<p>This member contains valid data only if the <b>ValidBits.IdInfo</b> bit is set.</p>
</dd>

### -field MemoryNumber

<dd>
<p>The number of memory mapped register address/data pair values from the PCI device that are included in the <b>RegisterDataPairs</b> member.</p>
<p>This member contains valid data only if the <b>ValidBits.MemoryNumber</b> bit is set.</p>
</dd>

### -field IoNumber

<dd>
<p>The number of I/O mapped register address/data pair values from the PCI device that are included in the <b>RegisterDataPairs</b> member.</p>
<p>This member contains valid data only if the <b>ValidBits.IoNumber</b> bit is set.</p>
</dd>

### -field RegisterDataPairs

<dd>
<p>An array of WHEA_PCIXDEVICE_REGISTER_PAIR structures that contains the register address/data pair values for the PCI device. The WHEA_PCIXDEVICE_REGISTER_PAIR structure is defined as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct WHEA_PCIXDEVICE_REGISTER_PAIR {
  ULONGLONG  Register;
  ULONGLONG  Data;
} WHEA_PCIXDEVICE_REGISTER_PAIR, *PWHEA_PCIXDEVICE_REGISTER_PAIR;</pre>
</td>
</tr>
</table></span></div>
<p></p>
<dl>

### -field Register

<dd>
<p>The address of the register.</p>
</dd>

### -field Data

<dd>
<p>The data contained in the register.</p>
</dd>
</dl>
<p>This member contains valid data only if the <b>ValidBits.RegisterDataPairs</b> bit is set.</p>
</dd>
</dl>

## -remarks
<p>The WHEA_PCIXDEVICE_ERROR_SECTION structure describes the error data that is contained in a PCI/PCI-X device error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a PCI/PCI-X device error section only if the <b>SectionType </b>member of one of the <a href="..\ntddk\ns-ntddk--whea-error-record-section-descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains PCIXBUS_ERROR_SECTION_GUID.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
<a href="whea.whea_error_packet">WHEA_ERROR_PACKET</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-record-section-descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-status.md">WHEA_ERROR_STATUS</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-pcixdevice-error-section-validbits.md">WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PCIXDEVICE_ERROR_SECTION structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
