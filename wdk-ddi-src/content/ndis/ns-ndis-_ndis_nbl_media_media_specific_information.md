---
UID: NS.NDIS._NDIS_NBL_MEDIA_MEDIA_SPECIFIC_INFORMATION
title: _NDIS_NBL_MEDIA_MEDIA_SPECIFIC_INFORMATION
author: windows-driver-content
description: The NDIS_NBL_MEDIA_SPECIFIC_INFORMATION structure specifies media-specific data that is associated with a NET_BUFFER_LIST structure.
old-location: netvista\ndis_nbl_media_specific_information.htm
old-project: netvista
ms.assetid: 01c0d9bb-5935-4b61-a04d-f9fcc5457152
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_NBL_MEDIA_MEDIA_SPECIFIC_INFORMATION, NDIS_NBL_MEDIA_SPECIFIC_INFORMATION, *PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_NBL_MEDIA_SPECIFIC_INFORMATION
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
---

# _NDIS_NBL_MEDIA_MEDIA_SPECIFIC_INFORMATION structure



## -description
The NDIS_NBL_MEDIA_SPECIFIC_INFORMATION structure specifies media-specific data that is associated
  with a 
  <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure.



## -syntax

````
typedef struct _NDIS_NBL_MEDIA_MEDIA_SPECIFIC_INFORMATION {
  PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION NextEntry;
  ULONG                                Tag;
  UCHAR                                Data[1];
} NDIS_NBL_MEDIA_SPECIFIC_INFORMATION, *PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION;
````


## -struct-fields

### -field NextEntry

A pointer to the next media-specific information structure in a linked list.


### -field Tag

A unique pre-assigned value that identifies the type of the media-specific information. This
     member is reserved for system use.
     

New tags can be assigned in future system releases for new media types that require additional OOB
     data specific to a particular media type.


### -field Data

A variable sized UCHAR array that contains the media-specific information.


## -remarks
Any driver in an NDIS driver stack can allocate and manage media-specific information. The
    media-specific information is in a linked list of NDIS_NBL_MEDIA_SPECIFIC_INFORMATION structures that
    contain driver-allocated and driver-defined data. Structures in the list contain any media-specific
    out-of-band (OOB) data that accompanies the 
    <a href="netvista.net_buffer">NET_BUFFER</a> structures associated with a 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure.

If a protocol driver allocated the OOB data, it configured the data for a send operation. If a
    miniport driver allocated the data, it configured the data for a receive indication.

To access NDIS_NBL_MEDIA_SPECIFIC_INFORMATION structures in a linked list, use the 
    <a href="netvista.ndis_nbl_add_media_specific_info">
    NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO</a>, 
    <a href="netvista.ndis_nbl_get_media_specific_info">
    NDIS_NBL_GET_MEDIA_SPECIFIC_INFO</a>, and 
    <a href="netvista.ndis_nbl_remove_media_specific_info">
    NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO</a> macros.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use <a href="netvista.ndis_nbl_media_specific_information_ex">NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX</a>.

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
<a href="netvista.ndis_nbl_add_media_specific_info">
   NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO</a>
</dt>
<dt>
<a href="netvista.ndis_nbl_get_media_specific_info">
   NDIS_NBL_GET_MEDIA_SPECIFIC_INFO</a>
</dt>
<dt>
<a href="netvista.ndis_nbl_media_specific_information_ex">NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX</a>
</dt>
<dt>
<a href="netvista.ndis_nbl_remove_media_specific_info">
   NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NBL_MEDIA_SPECIFIC_INFORMATION structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

