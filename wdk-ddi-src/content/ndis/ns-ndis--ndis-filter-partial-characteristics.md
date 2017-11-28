---
UID: NS.ndis._NDIS_FILTER_PARTIAL_CHARACTERISTICS
title: NDIS_FILTER_PARTIAL_CHARACTERISTICS
author: windows-driver-content
description: To specify optional entry points for a filter module, a filter driver initializes an NDIS_FILTER_PARTIAL_CHARACTERISTICS structure and passes it to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_filter_partial_characteristics.htm
old-project: netvista
ms.assetid: 4a7f365c-a252-4d8e-bddf-684b3298db5c
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NDIS_FILTER_PARTIAL_CHARACTERISTICS, NDIS_FILTER_PARTIAL_CHARACTERISTICS, *PNDIS_FILTER_PARTIAL_CHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_FILTER_PARTIAL_CHARACTERISTICS
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.iface: 
---

# NDIS_FILTER_PARTIAL_CHARACTERISTICS structure



## -description
<p>To specify optional entry points for a filter module, a filter driver initializes an
  NDIS_FILTER_PARTIAL_CHARACTERISTICS structure and passes it to the 
  <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">
  NdisSetOptionalHandlers</a> function.</p>


## -syntax

````
typedef struct _NDIS_FILTER_PARTIAL_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                            Header;
  ULONG                                         Flags;
  FILTER_SEND_NET_BUFFER_LISTS_HANDLER          SendNetBufferListsHandler;
  FILTER_SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER SendNetBufferListsCompleteHandler;
  FILTER_CANCEL_SEND_HANDLER                    CancelSendNetBufferListsHandler;
  FILTER_RECEIVE_NET_BUFFER_LISTS_HANDLER       ReceiveNetBufferListsHandler;
  FILTER_RETURN_NET_BUFFER_LISTS_HANDLER        ReturnNetBufferListsHandler;
} NDIS_FILTER_PARTIAL_CHARACTERISTICS, *PNDIS_FILTER_PARTIAL_CHARACTERISTICS;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     filter driver partial characteristics structure (NDIS_FILTER_PARTIAL_CHARACTERISTICS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_PARTIAL_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_FILTER_PARTIAL_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_FILTER_PARTIAL_CHARACTERISTICS_REVISION_1.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Reserved for NDIS.</p>
</dd>

### -field <b>SendNetBufferListsHandler</b>

<dd>
<p>The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter-send-net-buffer-lists.md">
     FilterSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.</p>
</dd>

### -field <b>SendNetBufferListsCompleteHandler</b>

<dd>
<p>The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter-send-net-buffer-lists-complete.md">
     FilterSendNetBufferListsComplete</a> function. To bypass this function, set this member to
     <b>NULL</b>.</p>
</dd>

### -field <b>CancelSendNetBufferListsHandler</b>

<dd>
<p>The entry point of the caller's 
     <a href="netvista.filtercancelsendnetbufferlists">
     FilterCancelSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.</p>
</dd>

### -field <b>ReceiveNetBufferListsHandler</b>

<dd>
<p>The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter-receive-net-buffer-lists.md">
     FilterReceiveNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.</p>
</dd>

### -field <b>ReturnNetBufferListsHandler</b>

<dd>
<p>The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter-return-net-buffer-lists.md">
     FilterReturnNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.</p>
</dd>
</dl>

## -remarks
<p>This structure specifies optional 
    <i>FilterXxx</i> functions and other characteristics for a filter module. These characteristics override
    the default values that the driver set in the 
    <a href="..\ndis\ns-ndis--ndis-filter-driver-characteristics.md">
    NDIS_FILTER_DRIVER_CHARACTERISTICS</a> structure that the driver passed to the 
    <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.filtercancelsendnetbufferlists">
   FilterCancelSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter-receive-net-buffer-lists.md">FilterReceiveNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter-return-net-buffer-lists.md">FilterReturnNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter-send-net-buffer-lists.md">FilterSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter-send-net-buffer-lists-complete.md">
   FilterSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-filter-driver-characteristics.md">
   NDIS_FILTER_DRIVER_CHARACTERISTICS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_FILTER_PARTIAL_CHARACTERISTICS structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
