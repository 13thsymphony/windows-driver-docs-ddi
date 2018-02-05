---
UID : NS:wwan._WWAN_DEVICE_SLOT_MAPPING_INFO
title : "_WWAN_DEVICE_SLOT_MAPPING_INFO"
author : windows-driver-content
description : The WWAN_DEVICE_SLOT_MAPPING_INFO structure represents the executor-to-slot mapping relationship in the MB device.
old-location : netvista\wwan_device_slot_mappings.htm
old-project : netvista
ms.assetid : 48DD867C-1235-4955-A01E-FF46C850DA31
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.wwan_device_slot_mappings, _WWAN_DEVICE_SLOT_MAPPING_INFO, WWAN_DEVICE_SLOT_MAPPING_INFO structure [Network Drivers Starting with Windows Vista], PWWAN_DEVICE_SLOT_MAPPING_INFO, wwan/PWWAN_DEVICE_SLOT_MAPPING_INFO, wwan/WWAN_DEVICE_SLOT_MAPPING_INFO, PWWAN_DEVICE_SLOT_MAPPING_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SLOT_MAPPING_INFO, *PWWAN_DEVICE_SLOT_MAPPING_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wwan.h
req.include-header : Wwan.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1703
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WWAN_DEVICE_SLOT_MAPPING_INFO, *PWWAN_DEVICE_SLOT_MAPPING_INFO
req.product : Windows 10 or later.
---

# _WWAN_DEVICE_SLOT_MAPPING_INFO structure
The WWAN_DEVICE_SLOT_MAPPING_INFO structure represents the executor-to-slot mapping relationship in the MB device.

## Syntax
````
typedef struct _WWAN_DEVICE_SLOT_MAPPING_INFO {
  ULONG            MapCount;
  WWAN_LIST_HEADER SlotMapList;
} WWAN_DEVICE_SLOT_MAPPING_INFO, *PWWAN_DEVICE_SLOT_MAPPING_INFO;
````

## Members


`SlotMapListHeader`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1703 Windows 10, version 1703 |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_device_slot_mapping_info.md">NDIS_WWAN_DEVICE_SLOT_MAPPING_INFO</a>

<a href="https://msdn.microsoft.com/54AF3447-7918-49CE-945A-DC8DC1E78CBF">OID_WWAN_DEVICE_SLOT_MAPPING_INFO</a>

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_set_device_slot_mapping_info.md">NDIS_WWAN_SET_DEVICE_SLOT_MAPPING_INFO</a>

<a href="https://msdn.microsoft.com/7825C20E-FB56-420D-B516-1ADA0C7C382E">NDIS_STATUS_WWAN_DEVICE_SLOT_MAPPING_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_DEVICE_SLOT_MAPPING_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>