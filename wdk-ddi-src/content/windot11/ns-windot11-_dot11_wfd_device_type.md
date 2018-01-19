---
UID : NS:windot11._DOT11_WFD_DEVICE_TYPE
title : _DOT11_WFD_DEVICE_TYPE
author : windows-driver-content
description : The DOT11_WFD_DEVICE_TYPE structure is used to specify primary and secondary device types.
old-location : netvista\dot11_wfd_device_type.htm
old-project : netvista
ms.assetid : 4AE7C35B-D2EA-4987-8195-EDD472C39681
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _DOT11_WFD_DEVICE_TYPE, *PDOT11_WFD_DEVICE_TYPE, DOT11_WFD_DEVICE_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : windot11.h
req.include-header : Windot11.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with   Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DOT11_WFD_DEVICE_TYPE
req.alt-loc : Windot11.h
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
req.typenames : "*PDOT11_WFD_DEVICE_TYPE, DOT11_WFD_DEVICE_TYPE"
req.product : Windows 10 or later.
---

# _DOT11_WFD_DEVICE_TYPE structure


## Syntax
````
typedef struct _DOT11_WFD_DEVICE_TYPE {
  USHORT   CategoryID;
  USHORT   SubCategoryID;
  UCHAR    OUI[4];
} DOT11_WFD_DEVICE_TYPE, *PDOT11_WFD_DEVICE_TYPE;
````

## Members

        
            `CategoryID`

            The identifier of the main type category.
        
            `SubCategoryID`

            The identifier of the type subcategory.

    ## Remarks
        The <b>DOT11_WFD_DEVICE_TYPE</b> data is provided in host byte-ordering. The miniport may need to convert the data to an ordering appropriate for inclusion in Peer-to-Peer Information Elements.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | windot11.h (include Windot11.h) |