---
UID: NS.NDIS._NDIS_FILTER_PARTIAL_CHARACTERISTICS
title: _NDIS_FILTER_PARTIAL_CHARACTERISTICS
author: windows-driver-content
description: To specify optional entry points for a filter module, a filter driver initializes an NDIS_FILTER_PARTIAL_CHARACTERISTICS structure and passes it to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_filter_partial_characteristics.htm
old-project: netvista
ms.assetid: 4a7f365c-a252-4d8e-bddf-684b3298db5c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_FILTER_PARTIAL_CHARACTERISTICS, NDIS_FILTER_PARTIAL_CHARACTERISTICS, *PNDIS_FILTER_PARTIAL_CHARACTERISTICS
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
req.irql: Any level
---

# _NDIS_FILTER_PARTIAL_CHARACTERISTICS structure



## -description
To specify optional entry points for a filter module, a filter driver initializes an
  NDIS_FILTER_PARTIAL_CHARACTERISTICS structure and passes it to the 
  <a href="netvista.ndissetoptionalhandlers">
  NdisSetOptionalHandlers</a> function.


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

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     filter driver partial characteristics structure (NDIS_FILTER_PARTIAL_CHARACTERISTICS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_PARTIAL_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_FILTER_PARTIAL_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_FILTER_PARTIAL_CHARACTERISTICS_REVISION_1.

### -field Flags

Reserved for NDIS.

### -field SendNetBufferListsHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">
     FilterSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.

### -field SendNetBufferListsCompleteHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
     FilterSendNetBufferListsComplete</a> function. To bypass this function, set this member to
     <b>NULL</b>.

### -field CancelSendNetBufferListsHandler

The entry point of the caller's 
     <a href="netvista.filtercancelsendnetbufferlists">
     FilterCancelSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.

### -field ReceiveNetBufferListsHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">
     FilterReceiveNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.

### -field ReturnNetBufferListsHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_return_net_buffer_lists.md">
     FilterReturnNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.

## -remarks
This structure specifies optional 
    <i>FilterXxx</i> functions and other characteristics for a filter module. These characteristics override
    the default values that the driver set in the 
    <a href="netvista.ndis_filter_driver_characteristics">
    NDIS_FILTER_DRIVER_CHARACTERISTICS</a> structure that the driver passed to the 
    <a href="netvista.ndisfregisterfilterdriver">
    NdisFRegisterFilterDriver</a> function.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported in NDIS 6.0 and later.
</td>
</tr>
<tr>
<th width="30%">
Header
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
<a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">FilterReceiveNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_return_net_buffer_lists.md">FilterReturnNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">FilterSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
   FilterSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="netvista.ndis_filter_driver_characteristics">
   NDIS_FILTER_DRIVER_CHARACTERISTICS</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="netvista.ndissetoptionalhandlers">NdisSetOptionalHandlers</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_FILTER_PARTIAL_CHARACTERISTICS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
