---
UID: NE.ndis._NDIS_MSIX_TABLE_CONFIG
title: _NDIS_MSIX_TABLE_CONFIG
author: windows-driver-content
description: The NDIS_MSIX_TABLE_OPERATION enumeration identifies the type of MSI-X configuration operation.
old-location: netvista\ndis_msix_table_operation.htm
old-project: netvista
ms.assetid: 7d1a4bb6-5db8-48b0-9be3-7468360951a1
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_MSIX_TABLE_CONFIG, *PNDIS_MSIX_TABLE_OPERATION, NDIS_MSIX_TABLE_OPERATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_MSIX_TABLE_OPERATION
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
req.irql: PASSIVE_LEVEL
---

# _NDIS_MSIX_TABLE_CONFIG enumeration



## -description
The NDIS_MSIX_TABLE_OPERATION enumeration identifies the type of MSI-X configuration
  operation.



## -syntax

````
typedef enum _NDIS_MSIX_TABLE_CONFIG { 
  NdisMSIXTableConfigSetTableEntry,
  NdisMSIXTableConfigMaskTableEntry,
  NdisMSIXTableConfigUnmaskTableEntry,
  NdisMSIXTableConfigMax
} NDIS_MSIX_TABLE_OPERATION, *PNDIS_MSIX_TABLE_OPERATION;
````


## -enum-fields

### -field NdisMSIXTableConfigSetTableEntry

The MSI-X table entry should be mapped to an MSI-X message that the bus driver allocated to the
     device.


### -field NdisMSIXTableConfigMaskTableEntry

The interrupts from an MSI-X table entry source should be masked.


### -field NdisMSIXTableConfigUnmaskTableEntry

The interrupts from an MSI-X table entry source should be unmasked.


### -field NdisMSIXTableConfigMax

The number of enumeration values in NDIS_MSIX_TABLE_OPERATION.


## -remarks
The NDIS_MSIX_TABLE_OPERATION enumeration is used in the 
    <a href="netvista.ndis_msix_config_parameters">
    NDIS_MSIX_CONFIG_PARAMETERS</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.1 and later.

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
<a href="netvista.ndis_msix_config_parameters">NDIS_MSIX_CONFIG_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MSIX_TABLE_OPERATION enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

