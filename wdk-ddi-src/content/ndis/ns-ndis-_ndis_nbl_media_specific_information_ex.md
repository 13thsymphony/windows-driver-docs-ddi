---
UID: NS:ndis._NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
title: "_NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX"
author: windows-driver-content
description: The NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure defines media-specific information that is associated with a NET_BUFFER_LIST structure.
old-location: netvista\ndis_nbl_media_specific_information_ex.htm
old-project: netvista
ms.assetid: f2c74fc3-45e2-4541-81a1-eb022e24cede
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure [Network Drivers Starting with Windows Vista], PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, ndis/NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, ndis/PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, ndis_netbuf_macros_media_specific_587542fc-f693-4a93-b343-0a9e86e6659e.xml, netvista.ndis_nbl_media_specific_information_ex"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
product: Windows
targetos: Windows
req.typenames: NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, *PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
---

# _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure
The <b>NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX</b> structure defines media-specific information that is
  associated with a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

## Syntax
````
typedef struct _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX {
  NDIS_OBJECT_HEADER                             Header;
  struct _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX  *NextEntry;
  ULONG                                          Tag;
  PVOID                                          Data;
} NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, *PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX;
````

## Members


`_NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX`



`Data`

A pointer to a buffer that contains the media-specific information.

`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     structure (NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_NBL_MEDIA_SPECIFIC_INFO_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_NBL_MEDIA_SPECIFIC_INFO_REVISION_1.

`NextEntry`

A pointer to the next NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure in a linked list of
     NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structures. If this is the last structure in the list, the
     pointer is <b>NULL</b>. Drivers must use the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff566518">
     NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX</a>, 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff566512">
     NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX</a>, and 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff566518">
     NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX</a> macros to manipulate this list.

`Tag`

A unique value (assigned by Microsoft) that identifies the type of media-specific information.
     This member is reserved for system use.
     

New tags can be assigned in future system releases for new media types that require additional OOB
     data specific to a particular media type.

## Remarks
NDIS 6.20 and later drivers should use the NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure to specify
    media-specific information. Any driver in an NDIS driver stack can allocate and manage media-specific
    information. The media-specific information is specified in a NULL-terminated linked list of
    NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structures, and each structure contains driver-allocated and
    driver-defined data.

Structures in the list contain any media-specific out-of-band (OOB) data that accompanies the 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures that are associated with a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

If a protocol driver allocated the OOB data, it configured the data for a send operation. If a
    miniport driver allocated the data, it configured the data for a receive indication.

To get the first element in the linked list, an NDIS driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro and specifies
    the 
    <b>MediaSpecificInformationEx</b> information type.

To add, get, and remove NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structures in the linked list, use the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff566518">
    NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX</a>, 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff566512">
    NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX</a>, and 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff566518">
    NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX</a> macros.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff566518">
   NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff566518">
   NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>



<a href="..\ndis\ns-ndis-_ndis_nbl_media_media_specific_information.md">NDIS_NBL_MEDIA_SPECIFIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff566512">
   NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>