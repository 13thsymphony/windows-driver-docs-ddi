---
UID: NE:ntddstor._STORAGE_QUERY_TYPE
title: "_STORAGE_QUERY_TYPE"
author: windows-driver-content
description: The STORAGE_QUERY_TYPE enumeration is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the properties of a storage device or adapter.
old-location: storage\storage_query_type.htm
old-project: storage
ms.assetid: 3f346a09-071e-4512-bf77-994d277cef4d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/PropertyMaskQuery, ntddstor/PropertyStandardQuery, PSTORAGE_QUERY_TYPE, storage.storage_query_type, ntddstor/STORAGE_QUERY_TYPE, ntddstor/PSTORAGE_QUERY_TYPE, PropertyMaskQuery, PropertyQueryMaxDefined, PropertyStandardQuery, ntddstor/PropertyQueryMaxDefined, STORAGE_QUERY_TYPE enumeration [Storage Devices], *PSTORAGE_QUERY_TYPE, PropertyExistsQuery, STORAGE_QUERY_TYPE, PSTORAGE_QUERY_TYPE enumeration pointer [Storage Devices], ntddstor/PropertyExistsQuery, structs-general_e76c71e4-e6ef-40d0-a0e7-5a21102efb1b.xml, _STORAGE_QUERY_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_QUERY_TYPE
product: Windows
targetos: Windows
req.typenames: STORAGE_QUERY_TYPE, *PSTORAGE_QUERY_TYPE
---

# _STORAGE_QUERY_TYPE Enumeration
The STORAGE_QUERY_TYPE enumeration is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the properties of a storage device or adapter.

## Syntax
````
typedef enum _STORAGE_QUERY_TYPE { 
  PropertyStandardQuery    = 0,
  PropertyExistsQuery,
  PropertyMaskQuery,
  PropertyQueryMaxDefined
} STORAGE_QUERY_TYPE, *PSTORAGE_QUERY_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>PropertyExistsQuery</td>
                    <td>Instructs the port driver to report whether the descriptor is supported.</td>
                </tr>
            
                <tr>
                    <td>PropertyMaskQuery</td>
                    <td>Not currently supported. Do not use.</td>
                </tr>
            
                <tr>
                    <td>PropertyQueryMaxDefined</td>
                    <td>Specifies the upper limit of the list of query types. This is used to validate the query type.</td>
                </tr>
            
                <tr>
                    <td>PropertyStandardQuery</td>
                    <td>Instructs the port driver to report a device descriptor, an adapter descriptor or a unique hardware device ID (DUID).</td>
                </tr>
</table>

    ## Remarks

        Caller specifies the type of query by choosing one of the enumeration values.

Caller defines the exact nature of an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request by specifying the query type together with the property ID. See <a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a> for an explanation of how these two values are combined to define the query.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |

    ## See Also

        <a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_QUERY_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>