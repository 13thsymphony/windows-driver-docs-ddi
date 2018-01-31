---
UID : NS:ntddndis._NDIS_WMI_ENUM_ADAPTER
title : "_NDIS_WMI_ENUM_ADAPTER"
author : windows-driver-content
description : The NDIS_WMI_ENUM_ADAPTER structure is returned when NDIS responds to the GUID_NDIS_ENUMERATE_ADAPTERS_EX GUID.
old-location : netvista\ndis_wmi_enum_adapter.htm
old-project : netvista
ms.assetid : 89fa481a-b6f4-4948-8fda-e1e19c58da28
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PNDIS_WMI_ENUM_ADAPTER, ntddndis/PNDIS_WMI_ENUM_ADAPTER, ndis_wmi_ref_a64c64b4-2108-4b99-937d-098197c5a72c.xml, netvista.ndis_wmi_enum_adapter, NDIS_WMI_ENUM_ADAPTER structure [Network Drivers Starting with Windows Vista], ntddndis/NDIS_WMI_ENUM_ADAPTER, PNDIS_WMI_ENUM_ADAPTER structure pointer [Network Drivers Starting with Windows Vista], *PNDIS_WMI_ENUM_ADAPTER, NDIS_WMI_ENUM_ADAPTER, _NDIS_WMI_ENUM_ADAPTER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_WMI_ENUM_ADAPTER, NDIS_WMI_ENUM_ADAPTER"
---

# _NDIS_WMI_ENUM_ADAPTER structure
The NDIS_WMI_ENUM_ADAPTER structure is returned when NDIS responds to the 
  <mshelp:link keywords="netvista.guid_ndis_enumerate_adapters_ex" tabindex="0">
  GUID_NDIS_ENUMERATE_ADAPTERS_EX</mshelp:link> GUID.

## Syntax
````
typedef struct _NDIS_WMI_ENUM_ADAPTER {
  NDIS_OBJECT_HEADER Header;
  NET_IFINDEX        IfIndex;
  NET_LUID           NetLuid;
  USHORT             DeviceNameLength;
  CHAR               DeviceName[1];
} NDIS_WMI_ENUM_ADAPTER, *PNDIS_WMI_ENUM_ADAPTER;
````

## Members


`DeviceName`

The device name of the NDIS miniport adapter interface that is associated with the GUID. The
     device name is a null-terminated wide character string.

`DeviceNameLength`

The length, in bytes, of the device name of the NDIS miniport adapter interface that is associated
     with the GUID.

`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for this
     NDIS_WMI_ENUM_ADAPTER structure. Set the 
     <b>Type</b> member of NDIS_OBJECT_HEADER to NDIS_WMI_OBJECT_TYPE_ENUM_ADAPTER, the 
     <b>Revision</b> member to NDIS_WMI_ENUM_ADAPTER_REVISION_1, and the 
     <b>Size</b> member to 
     sizeof(NDIS_WMI_ENUM_ADAPTER).

`IfIndex`

The NDIS interface index of the NDIS miniport adapter interface that is associated with the
     GUID.

`NetLuid`

The NDIS network interface name of the miniport adapter.

## Remarks
NDIS returns the NDIS_WMI_ENUM_ADAPTER structure when it enumerates miniport adapters for WMI clients.
    For more information about enumerating miniport adapters for WMI clients, see 
    <mshelp:link keywords="netvista.guid_ndis_enumerate_adapters_ex" tabindex="0">
    GUID_NDIS_ENUMERATE_ADAPTERS_EX</mshelp:link>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff552617">GUID_NDIS_ENUMERATE_ADAPTERS_EX</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WMI_ENUM_ADAPTER structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>