---
UID: NF.portcls.IMiniportWaveRTOutputStream.SetWritePacket
title: IMiniportWaveRTOutputStream::SetWritePacket
author: windows-driver-content
description: SetWritePacket informs the driver that the OS has written valid data to the WaveRT buffer.
old-location: audio\iminiportwavertoutputstream_setwritepacket.htm
old-project: audio
ms.assetid: 28C73FBA-9122-4CFD-959E-495062CEEF41
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: IMiniportWaveRTOutputStream, SetWritePacket, IMiniportWaveRTOutputStream::SetWritePacket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMiniportWaveRTOutputStream.SetWritePacket
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Passive level
req.iface: IMiniportWaveRTOutputStream
---

# IMiniportWaveRTOutputStream::SetWritePacket method



## -description
<p>SetWritePacket informs the driver that the OS has written valid data to the WaveRT buffer. </p>


## -syntax

````
NTSTATUS SetWritePacket(
  [in] ULONG     PacketNumber,
  [in] DWORD     Flags,
  [in] ULONGLONG EosPacketLength
);
````


## -parameters
<dl>

### -param <i>PacketNumber</i> [in]

<dd>
<p>The number of the packet written by the OS to the WaveRT buffer. </p>
</dd>

### -param <i>Flags</i> [in]

<dd>
<p>Additional attributes related to the packet or stream.</p>
<p>KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM - This flag indicates that this packet represents the end of the data stream.</p>
</dd>

### -param <i>EosPacketLength</i> [in]

<dd>
<p>The length of the EOS packet if KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM is specified in Flags. Zero is a valid value. If KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM is not specified in Flags, this parameter is ignored.</p>
</dd>
</dl>

## -returns
<p><code>SetWritePacket</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the function returns an appropriate error status code.</p>

<p>STATUS_DATA_LATE_ERROR – The driver returns this error if the OS passes a packet number that has already transferred or is currently transferring. In this case, a glitch condition has occurred. The driver may optionally use some of the data from the packet or continue playing out the data previously written to this packet number. 

</p>

<p>STATUS_DATA_OVERRUN – The driver returns this error if the OS passes a packet number that is higher than can be stored in the WaveRT buffer. In this case, a glitch condition has occurred. The driver may optionally ignore the data in the packet. 

 
</p>

<p>STATUS_INVALID_DEVICE_STATE – The driver returns this error if the OS calls this routine after a previously setting the KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM flag. 

</p>

<p>STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status. This includes any Flag values not specifically defined above.</p>

## -remarks
<p>After the OS calls this routine, the driver may optionally use the provided information to optimize the hardware transfer. For example, the driver might optimize DMA transfers, or program hardware to stop transfer at the end of the specified packet in case the OS does not call this routine again to inform the driver of another packet. This can mitigate audible effects of underflow, for example introducing an audible gap rather than repeating a circular buffer. The driver however is still obligated to increase its internal packet counter and signal notification events at a nominal real time rate. 

</p>

<p>Except when the OS specifies the KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM flag, the packet size is the WaveRT buffer size divided by the NotificationCount passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536740">IMiniportWaveRTStreamNotification::AllocateBufferWithNotification</a>.  

</p>

<p>Depending on hardware capabilities, if the KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM flag is specified, the driver may silence-fill a portion of the WaveRT buffer that follows the EOS packet in case the hardware transfers data beyond the EOS position. 
 

</p>

<p>After the OS calls this routine, the driver may optionally use the provided information to optimize the hardware transfer. For example, the driver might optimize DMA transfers, or program hardware to stop transfer at the end of the specified packet in case the OS does not call this routine again to inform the driver of another packet. This can mitigate audible effects of underflow, for example introducing an audible gap rather than repeating a circular buffer. The driver however is still obligated to increase its internal packet counter and signal notification events at a nominal real time rate. 

</p>

<p>Except when the OS specifies the KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM flag, the packet size is the WaveRT buffer size divided by the NotificationCount passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536740">IMiniportWaveRTStreamNotification::AllocateBufferWithNotification</a>.  

</p>

<p>Depending on hardware capabilities, if the KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM flag is specified, the driver may silence-fill a portion of the WaveRT buffer that follows the EOS packet in case the hardware transfers data beyond the EOS position. 
 

</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 10 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p> Passive level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946534">IMiniportWaveRTOutputStream</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveRTOutputStream::SetWritePacket method%20 RELEASE:%20(11/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
