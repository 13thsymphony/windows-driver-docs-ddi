---
UID: NS.ntddcdrm._SUB_Q_HEADER
title: SUB_Q_HEADER
author: windows-driver-content
description: The SUB_Q_HEADER structure contains audio status information and the length of the Q subchannel data being returned. This structure is used in conjunction with SUB_Q_CHANNEL_DATA.
old-location: storage\sub_q_header.htm
ms.assetid: 3ee3657d-acdd-4d3f-9cff-eb4a494429b4
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SUB_Q_HEADER
req.alt-loc: ntddcdrm.h
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
ms.keywords: SUB_Q_HEADER, SUB_Q_HEADER, *PSUB_Q_HEADER
req.iface: 
---

# SUB_Q_HEADER structure



## -description
<p>The SUB_Q_HEADER structure contains audio status information and the length of the Q subchannel data being returned. This structure is used in conjunction with <a href="https://msdn.microsoft.com/library/windows/hardware/ff567595">SUB_Q_CHANNEL_DATA</a>.</p>


## -syntax

````
typedef struct _SUB_Q_HEADER {
  UCHAR Reserved;
  UCHAR AudioStatus;
  UCHAR DataLength[2];
} SUB_Q_HEADER, *PSUB_Q_HEADER;
````


## -struct-fields
<dl>

### -field <b>Reserved</b>

<dd>
<p>Reserved.</p>
</dd>

### -field <b>AudioStatus</b>

<dd>
<p>Reports the audio status with one of the following flags:</p>
<p></p>
<dl>

### -field <a id="AUDIO_STATUS_NOT_SUPPORTED"></a><a id="audio_status_not_supported"></a>AUDIO_STATUS_NOT_SUPPORTED

<dd>
<p>Audio status byte not supported or not valid.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="AUDIO_STATUS_IN_PROGRESS"></a><a id="audio_status_in_progress"></a>AUDIO_STATUS_IN_PROGRESS

<dd>
<p>Audio play operation is in progress.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="AUDIO_STATUS_PAUSED"></a><a id="audio_status_paused"></a>AUDIO_STATUS_PAUSED

<dd>
<p>Audio play operation is paused.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="AUDIO_STATUS_PLAY_COMPLETE"></a><a id="audio_status_play_complete"></a>AUDIO_STATUS_PLAY_COMPLETE

<dd>
<p>Audio play operation completed successfully.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="AUDIO_STATUS_PLAY_ERROR"></a><a id="audio_status_play_error"></a>AUDIO_STATUS_PLAY_ERROR

<dd>
<p>Audio play operation stopped due to error.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="AUDIO_STATUS_NO_STATUS"></a><a id="audio_status_no_status"></a>AUDIO_STATUS_NO_STATUS

<dd>
<p>No current audio status to return.</p>
</dd>
</dl>
</dd>

### -field <b>DataLength</b>

<dd>
<p>Gives the length of Q subchannel data that follows this header structure. The bytes in this array are arranged in big-endian order. <b>DataLength</b>[0] contains the most significant byte, and <b>DataLength</b>[1] contains the least significant byte. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559363">IOCTL_CDROM_READ_Q_CHANNEL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551371">CDROM_SUB_Q_DATA_FORMAT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567595">SUB_Q_CHANNEL_DATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20SUB_Q_HEADER structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
