---
UID : NS:ndis._NDIS_MSIX_CONFIG_PARAMETERS
title : _NDIS_MSIX_CONFIG_PARAMETERS
author : windows-driver-content
description : The NDIS_MSIX_CONFIG_PARAMETERS structure defines a requested configuration operation and specifies the parameters that are required for that particular operation.
old-location : netvista\ndis_msix_config_parameters.htm
old-project : netvista
ms.assetid : 52c3238f-4d3a-4241-95bf-630e57e8a6e1
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_MSIX_CONFIG_PARAMETERS, NDIS_MSIX_CONFIG_PARAMETERS, *PNDIS_MSIX_CONFIG_PARAMETERS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.1 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_MSIX_CONFIG_PARAMETERS
req.alt-loc : ndis.h
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
req.typenames : NDIS_MSIX_CONFIG_PARAMETERS, *PNDIS_MSIX_CONFIG_PARAMETERS
---

# _NDIS_MSIX_CONFIG_PARAMETERS structure
The NDIS_MSIX_CONFIG_PARAMETERS structure defines a requested configuration operation and specifies
  the parameters that are required for that particular operation.

## Syntax
````
typedef struct _NDIS_MSIX_CONFIG_PARAMETERS {
  NDIS_OBJECT_HEADER        Header;
  NDIS_MSIX_TABLE_OPERATION ConfigOperation;
  ULONG                     TableEntry;
  ULONG                     MessageNumber;
} NDIS_MSIX_CONFIG_PARAMETERS, *PNDIS_MSIX_CONFIG_PARAMETERS;
````

## Members

        
            `ConfigOperation`

            The requested configuration operation for a MSI-X table entry. This operation is specified as one
     of the values from the 
     <a href="..\ndis\ne-ndis-_ndis_msix_table_config.md">
     NDIS_MSIX_TABLE_OPERATION</a> enumeration.
        
            `Header`

            The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MSIX_CONFIG_PARAMETERS structure. The miniport driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_MSIX_CONFIG_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MSIX_CONFIG_PARAMETERS_REVISION_1.
        
            `MessageNumber`

            The MSI-X message number that is assigned to the device. This value is required for the 
     <b>NdisMSIXTableConfigSetTableEntry</b> operation. This parameter is not used for the 
     <b>NdisMSIXTableConfigMaskTableEntry</b> or 
     <b>NdisMSIXTableConfigUnmaskTableEntry</b> operations.
        
            `TableEntry`

            The MSI-X table entry index.

    ## Remarks
        To mask, unmask, or map MSI-X table entries, an NDIS driver passes the NDIS_MSIX_CONFIG_PARAMETERS
    structure to the 
    <a href="..\ndis\nf-ndis-ndismconfigmsixtableentry.md">
    NdisMConfigMSIXTableEntry</a> function. NDIS_MSIX_CONFIG_PARAMETERS defines a requested configuration
    operation and specifies the parameters that are required for that operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ndis\ne-ndis-_ndis_msix_table_config.md">NDIS_MSIX_TABLE_OPERATION</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismconfigmsixtableentry.md">NdisMConfigMSIXTableEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MSIX_CONFIG_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>