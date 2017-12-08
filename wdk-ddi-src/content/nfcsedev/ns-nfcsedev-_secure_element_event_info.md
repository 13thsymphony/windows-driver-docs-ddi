---
UID: NS.NFCSEDEV._SECURE_ELEMENT_EVENT_INFO
title: _SECURE_ELEMENT_EVENT_INFO
author: windows-driver-content
description: This structure provides information about a secure element event.
old-location: nfpdrivers\secure_element_event_info.htm
old-project: nfpdrivers
ms.assetid: 72B31C26-89D3-49B2-A404-E6F096D0A334
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _SECURE_ELEMENT_EVENT_INFO, *PSECURE_ELEMENT_EVENT_INFO, SECURE_ELEMENT_EVENT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SECURE_ELEMENT_EVENT_INFO
req.alt-loc: nfcsedev.h
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
---

# _SECURE_ELEMENT_EVENT_INFO structure



## -description
This structure provides information about a secure element event.


## -syntax

````
typedef struct _SECURE_ELEMENT_EVENT_INFO {
  GUID                                     guidSecureElementId;
  SECURE_ELEMENT_EVENT_TYPE                eEventType;
  DWORD                                    cbEventData;
  _Field_size_bytes_(cbEventData)
    BYTE pbEventData[ANYSIZE_ARRAY];
} SECURE_ELEMENT_EVENT_INFO, *PSECURE_ELEMENT_EVENT_INFO;
````


## -struct-fields

### -field guidSecureElementId

This is a unique identifier for the secure element.

### -field eEventType

This is an event type. For more information about the types, see the <a href="nfpdrivers._secure_element_event_type">SECURE_ELEMENT_EVENT_TYPE</a> enumeration topic.

### -field cbEventData

This is the amount of bytes for the pbEventData array.

### -field pbEventData[ANYSIZE_ARRAY]

This is the event data buffer. When <b>eEventType</b> is <b>HceActivated</b> or <b>HceDeactivated</b>, this member contains a pointer to a <a href="nfpdrivers.secure_element_hce_activation_payload">SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD</a> structure. The <b>bConnectionId</b> member in that structure is the same ID value that’s used in <a href="nfpdrivers._secure_element_hce_data_packet">SECURE_ELEMENT_HCE_DATA_PACKET</a> to send and receive an HCE packet with <a href="..\nfcsedev\ni-nfcsedev-ioctl_nfcse_hce_remote_send.md">IOCTL_NFCSE_HCE_REMOTE_SEND</a> and <a href="..\nfcsedev\ni-nfcsedev-ioctl_nfcse_hce_remote_recv.md">IOCTL_NFCSE_HCE_REMOTE_RECV</a>.
When <b>eEventType</b> is <b>ExternalReaderArrival</b> or <b>ExternalReaderDeparture</b>, <b>pbEventData</b> is empty and <b>cbEventData</b> is 0.
When <b>eEventType</b> is <b>Transaction</b>, <b>pbEventData</b> contains a list of parameters that is encoded in BER-TLV fields. This event is mapped to EVT_TRANSACTION.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Nfcsedev.h</dt>
</dl>
</td>
</tr>
</table>