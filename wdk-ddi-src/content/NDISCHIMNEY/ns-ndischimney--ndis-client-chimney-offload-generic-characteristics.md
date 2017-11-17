---
UID: NS.ndischimney._NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
title: NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
author: windows-driver-content
description: The NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies a protocol driver's generic chimney offload entry points.
old-location: netvista\ndis_client_chimney_offload_generic_characteristics.htm
ms.assetid: 66eb9528-e026-44cd-a775-c8d963036adc
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
req.alt-loc: ndischimney.h
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
ms.keywords: NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
req.iface: 
---

# NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>The NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies a protocol driver's
  generic chimney offload entry points. Generic chimney offload entry points apply to all chimney offload
  types. Currently, TCP chimney offload is the only defined chimney offload type.</p>


## -syntax

````
typedef struct _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                  Header;
  ULONG                               Flags;
  INITIATE_OFFLOAD_COMPLETE_HANDLER   InitiateOffloadCompleteHandler;
  TERMINATE_OFFLOAD_COMPLETE_HANDLER  TerminateOffloadCompleteHandler;
  UPDATE_OFFLOAD_COMPLETE_HANDLER     UpdateOffloadCompleteHandler;
  INVALIDATE_OFFLOAD_COMPLETE_HANDLER InvalidateOffloadCompleteHandler;
  QUERY_OFFLOAD_COMPLETE_HANDLER      QueryOffloadCompleteHandler;
  INDICATE_OFFLOAD_EVENT_HANDLER      IndicateOffloadEventHandler;
} NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The header of the NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure and the size of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>InitiateOffloadCompleteHandler</b>

<dd>
<p>Specifies the entry point of the driver's 
     <a href="https://msdn.microsoft.com/0300d841-b211-42f8-b60d-d7d37201e778">
     ProtocolInitiateOffloadComplete</a> function.</p>
</dd>

### -field <b>TerminateOffloadCompleteHandler</b>

<dd>
<p>The entry point of the driver's 
     <a href="https://msdn.microsoft.com/614d36e8-38ac-49a7-8711-7a6c6646309c">
     ProtocolTerminateOffloadComplete</a> function.</p>
</dd>

### -field <b>UpdateOffloadCompleteHandler</b>

<dd>
<p>The entry point of the driver's 
     <a href="https://msdn.microsoft.com/3cd7a32a-d560-429b-b191-aeabb87433f3">
     ProtocolUpdateOffloadComplete</a> function.</p>
</dd>

### -field <b>InvalidateOffloadCompleteHandler</b>

<dd>
<p>The entry point of the driver's 
     <a href="https://msdn.microsoft.com/6d2c71d0-9686-4eb5-9715-27de3dc8b390">
     ProtocolInvalidateOffloadComplete</a> function.</p>
</dd>

### -field <b>QueryOffloadCompleteHandler</b>

<dd>
<p>The entry point of the driver's 
     <a href="https://msdn.microsoft.com/f521af88-eb96-4077-8882-9b1d02c6c87c">
     ProtocolQueryOffloadComplete</a> function.</p>
</dd>

### -field <b>IndicateOffloadEventHandler</b>

<dd>
<p>The entry point of the driver's 
     <a href="https://msdn.microsoft.com/608c1c7c-1eb3-4d86-9471-313fce2df00e">
     ProtocolIndicateOffloadEvent</a> function.</p>
</dd>
</dl>

## -remarks
<p>To register its generic chimney offload entry points, a protocol or intermediate driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function,
    the protocol or intermediate driver passes a pointer to the
    NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/608c1c7c-1eb3-4d86-9471-313fce2df00e">
   ProtocolIndicateOffloadEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/0300d841-b211-42f8-b60d-d7d37201e778">
   ProtocolInitiateOffloadComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6d2c71d0-9686-4eb5-9715-27de3dc8b390">
   ProtocolInvalidateOffloadComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f521af88-eb96-4077-8882-9b1d02c6c87c">
   ProtocolQueryOffloadComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/614d36e8-38ac-49a7-8711-7a6c6646309c">
   ProtocolTerminateOffloadComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/3cd7a32a-d560-429b-b191-aeabb87433f3">
   ProtocolUpdateOffloadComplete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
