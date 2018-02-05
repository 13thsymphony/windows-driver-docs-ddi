---
UID : NS:ndis._NDIS_FILTER_ATTRIBUTES
title : "_NDIS_FILTER_ATTRIBUTES"
author : windows-driver-content
description : The NDIS_FILTER_ATTRIBUTES structure defines the attributes of a filter module.
old-location : netvista\ndis_filter_attributes.htm
old-project : netvista
ms.assetid : a377d809-4a6f-413e-a26a-446b4eca85ab
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ndis_filter_attributes, NDIS_FILTER_ATTRIBUTES, filter_structures_ref_8711cb33-bba0-41ba-912b-af351c7e758d.xml, _NDIS_FILTER_ATTRIBUTES, ndis/PNDIS_FILTER_ATTRIBUTES, *PNDIS_FILTER_ATTRIBUTES, NDIS_FILTER_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], ndis/NDIS_FILTER_ATTRIBUTES, PNDIS_FILTER_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], PNDIS_FILTER_ATTRIBUTES
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_FILTER_ATTRIBUTES, *PNDIS_FILTER_ATTRIBUTES
---

# _NDIS_FILTER_ATTRIBUTES structure
The NDIS_FILTER_ATTRIBUTES structure defines the attributes of a filter module.

## Syntax
````
typedef struct _NDIS_FILTER_ATTRIBUTES {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
} NDIS_FILTER_ATTRIBUTES, *PNDIS_FILTER_ATTRIBUTES;
````

## Members


`Flags`

Reserved. Set this member to zero.

`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     filter attributes structure (NDIS_FILTER_ATTRIBUTES). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_ATTRIBUTES, the 
     <b>Revision</b> member to NDIS_FILTER_ATTRIBUTES_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_FILTER_ATTRIBUTES_REVISION_1.

## Remarks
A filter drivers passes an NDIS_FILTER_ATTRIBUTES structure to the 
    <a href="..\ndis\nf-ndis-ndisfsetattributes.md">NdisFSetAttributes</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\nf-ndis-ndisfsetattributes.md">NdisFSetAttributes</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_FILTER_ATTRIBUTES structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>