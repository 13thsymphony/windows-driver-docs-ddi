---
UID: NS.NDIS._NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
title: _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
author: windows-driver-content
description: The NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure defines media-specific information that is associated with a NET_BUFFER_LIST structure.
old-location: netvista\ndis_nbl_media_specific_information_ex.htm
old-project: netvista
ms.assetid: f2c74fc3-45e2-4541-81a1-eb022e24cede
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, *PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
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

# _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure



## -description
The <b>NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX</b> structure defines media-specific information that is
  associated with a 
  <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure.



## -syntax

````
typedef struct _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX {
  NDIS_OBJECT_HEADER                             Header;
  struct _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX  *NextEntry;
  ULONG                                          Tag;
  PVOID                                          Data;
} NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, *PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX;
````


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     structure (NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_NBL_MEDIA_SPECIFIC_INFO_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_NBL_MEDIA_SPECIFIC_INFO_REVISION_1.


### -field NextEntry

A pointer to the next NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure in a linked list of
     NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structures. If this is the last structure in the list, the
     pointer is <b>NULL</b>. Drivers must use the 
     <a href="netvista.ndis_nbl_add_media_specific_info_ex">
     NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX</a>, 
     <a href="netvista.ndis_nbl_get_media_specific_info_ex">
     NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX</a>, and 
     <a href="netvista.ndis_nbl_remove_media_specific_info_ex">
     NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX</a> macros to manipulate this list.


### -field Tag

A unique value (assigned by Microsoft) that identifies the type of media-specific information.
     This member is reserved for system use.
     

New tags can be assigned in future system releases for new media types that require additional OOB
     data specific to a particular media type.


### -field Data

A pointer to a buffer that contains the media-specific information.


## -remarks
NDIS 6.20 and later drivers should use the NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure to specify
    media-specific information. Any driver in an NDIS driver stack can allocate and manage media-specific
    information. The media-specific information is specified in a NULL-terminated linked list of
    NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structures, and each structure contains driver-allocated and
    driver-defined data.

Structures in the list contain any media-specific out-of-band (OOB) data that accompanies the 
    <a href="netvista.net_buffer">NET_BUFFER</a> structures that are associated with a 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure.

If a protocol driver allocated the OOB data, it configured the data for a send operation. If a
    miniport driver allocated the data, it configured the data for a receive indication.

To get the first element in the linked list, an NDIS driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro and specifies
    the 
    <b>MediaSpecificInformationEx</b> information type.

To add, get, and remove NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structures in the linked list, use the 
    <a href="netvista.ndis_nbl_add_media_specific_info_ex">
    NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX</a>, 
    <a href="netvista.ndis_nbl_get_media_specific_info_ex">
    NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX</a>, and 
    <a href="netvista.ndis_nbl_remove_media_specific_info_ex">
    NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX</a> macros.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.20 and later.

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
<a href="netvista.ndis_nbl_add_media_specific_info_ex">
   NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX</a>
</dt>
<dt>
<a href="netvista.ndis_nbl_get_media_specific_info_ex">
   NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX</a>
</dt>
<dt>
<a href="netvista.ndis_nbl_media_specific_information">NDIS_NBL_MEDIA_SPECIFIC_INFORMATION</a>
</dt>
<dt>
<a href="netvista.ndis_nbl_remove_media_specific_info_ex">
   NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

