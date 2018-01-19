---
UID : NS:ndiswwan._NDIS_WWAN_MAC_INFO
title : _NDIS_WWAN_MAC_INFO
author : windows-driver-content
description : The NDIS_WWAN_MAC_INFO structure represents NDIS port information for a PDP context.
old-location : netvista\ndis_wwan_mac_info.htm
old-project : netvista
ms.assetid : C55DC50B-5A1B-496E-BBB8-8EB94A9CFD2F
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_WWAN_MAC_INFO, NDIS_WWAN_MAC_INFO, *PNDIS_WWAN_MAC_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndiswwan.h
req.include-header : Ndiswwan.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 8.1 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_WWAN_MAC_INFO
req.alt-loc : ndiswwan.h
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
req.typenames : NDIS_WWAN_MAC_INFO, *PNDIS_WWAN_MAC_INFO
---

# _NDIS_WWAN_MAC_INFO structure
The NDIS_WWAN_MAC_INFO structure represents NDIS port information for a PDP context.

## Syntax
````
typedef struct _NDIS_WWAN_MAC_INFO {
  ULONG                 uReserved;
  ULONG                 uNdisPortNumber;
  NDIS_WWAN_MAC_ADDRESS MacAddr;
} NDIS_WWAN_MAC_INFO, *PNDIS_WWAN_MAC_INFO;
````

## Members

        
            `MacAddr`

            The NDIS port of the PDP context.
        
            `uNdisPortNumber`

            The number of the NDIS port. This value is an NDIS_PORT_NUMBER value, which has a ULONG data type and is valid from zero through 0xffffff, where zero is reserved for the default port.
        
            `uReserved`

            Reserved. Do not use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndiswwan.h (include Ndiswwan.h) |