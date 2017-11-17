---
UID: NS.ksmedia._KSAUDIO_PACKETSIZE_CONSTRAINTS
title: KSAUDIO_PACKETSIZE_CONSTRAINTS
author: windows-driver-content
description: The KSAUDIO_PACKETSIZE_CONSTRAINTS structure describes the physical hardware constraints.
old-location: audio\ksaudio_packetsize_constraints.htm
ms.assetid: 6BD3E98A-A2A5-4285-8F41-1445F90DD8EB
ms.author: windowsdriverdev
ms.date: 10/30/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: audio
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSAUDIO_PACKETSIZE_CONSTRAINTS
req.alt-loc: ksmedia.h
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
ms.keywords: KSAUDIO_PACKETSIZE_CONSTRAINTS, KSAUDIO_PACKETSIZE_CONSTRAINTS
req.iface: 
---

# KSAUDIO_PACKETSIZE_CONSTRAINTS structure



## -description
<p>The <b>KSAUDIO_PACKETSIZE_CONSTRAINTS</b> structure describes the physical hardware constraints. It includes an array of 0 or more <a href="https://msdn.microsoft.com/library/windows/hardware/dn965562">KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</a> structures describing constraints specific to any signal processing modes.
The driver sets this property before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff537731">PcRegisterSubdevice</a> or otherwise enabling its KS filter interface for its streaming pins.</p>


## -syntax

````
typedef struct _KSAUDIO_PACKETSIZE_CONSTRAINTS {
  ULONG                                                                                   MinPacketPeriodInHns;
  ULONG                                                                                   PacketSizeFileAlignment;
  ULONG                                                                                   Reserved;
  ULONG                                                                                   NumProcessingModeConstraints;
  _Field_size_(NumProcessingModeConstraints) KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT ProcessingModeConstraints[ANYSIZE_ARRAY];
} KSAUDIO_PACKETSIZE_CONSTRAINTS, *PKSAUDIO_PACKETSIZE_CONSTRAINTS;
````


## -struct-fields
<dl>

### -field <b>MinPacketPeriodInHns</b>

<dd>
<p>The absolute minimum processing period supported by the driver expressed in hundred-nanosecond (HNS) units. This value can be 0 if the driver has no specific minimum processing period.</p>
</dd>

### -field <b>PacketSizeFileAlignment</b>

<dd>
<p>The byte size alignment requirement. Use one of these defined file alignment values:</p>
<dl><a id="FILE_BYTE_ALIGNMENT"></a><a id="file_byte_alignment"></a>
### -field <b>FILE_BYTE_ALIGNMENT</b>
<a id="FILE_WORD_ALIGNMENT"></a><a id="file_word_alignment"></a>
### -field <b>FILE_WORD_ALIGNMENT</b>
<a id="FILE_LONG_ALIGNMENT"></a><a id="file_long_alignment"></a>
### -field <b>FILE_LONG_ALIGNMENT</b>
<a id="FILE_QUAD_ALIGNMENT"></a><a id="file_quad_alignment"></a>
### -field <b>FILE_QUAD_ALIGNMENT</b>
<a id="FILE_OCTA_ALIGNMENT"></a><a id="file_octa_alignment"></a>
### -field <b>FILE_OCTA_ALIGNMENT</b>
<a id="FILE_32_BYTE_ALIGNMENT"></a><a id="file_32_byte_alignment"></a>
### -field <b>FILE_32_BYTE_ALIGNMENT</b>
<a id="FILE_64_BYTE_ALIGNMENT"></a><a id="file_64_byte_alignment"></a>
### -field <b>FILE_64_BYTE_ALIGNMENT</b>
<a id="FILE_128_BYTE_ALIGNMENT"></a><a id="file_128_byte_alignment"></a>
### -field <b>FILE_128_BYTE_ALIGNMENT</b>
<a id="FILE_256_BYTE_ALIGNMENT"></a><a id="file_256_byte_alignment"></a>
### -field <b>FILE_256_BYTE_ALIGNMENT</b>
<a id="FILE_512_BYTE_ALIGNMENT"></a><a id="file_512_byte_alignment"></a>
### -field <b>FILE_512_BYTE_ALIGNMENT</b>

</dl>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Unused.</p>
</dd>

### -field <b>NumProcessingModeConstraints</b>

<dd>
<p>The number of additional constraints for specific processing modes. This value can be 0.</p>
</dd>

### -field <b>ProcessingModeConstraints</b>

<dd>
<p>An array of 0 or more processing mode constraints. 
</p>
</dd>
</dl>

## -remarks
<p>The driver sets this variable length data structure as the value of the DEVPKEY_KsAudio_PacketSize_Constraints property on the PnP interface of the KS filter that has the streaming pins with the constraints. 
</p>

<p>For WaveRT drivers, this data structure describes the constraints for a WaveRT packet. Several WaveRT packets (typically 2) are concatenated to form the WaveRT buffer.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn965562">KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537731">PcRegisterSubdevice</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_PACKETSIZE_CONSTRAINTS structure%20 RELEASE:%20(10/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
