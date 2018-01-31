---
UID : NS:d4drvif._DOT4_DC_OPEN_DATA
title : "_DOT4_DC_OPEN_DATA"
author : windows-driver-content
description : This topic describes the DOT4_DC_OPEN_DATA structure.
old-location : print\dot4_dc_open_data.htm
old-project : print
ms.assetid : 72AE7A78-C02D-4C14-B017-9CEECF34FEDF
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PDOT4_DC_OPEN_DATA, DOT4_DC_OPEN_DATA, print.dot4_dc_open_data, d4drvif/PDOT4_DC_OPEN_DATA, PDOT4_DC_OPEN_DATA structure pointer [Print Devices], _DOT4_DC_OPEN_DATA, d4drvif/DOT4_DC_OPEN_DATA, DOT4_DC_OPEN_DATA structure [Print Devices], *PDOT4_DC_OPEN_DATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d4drvif.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
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
req.typenames : DOT4_DC_OPEN_DATA, *PDOT4_DC_OPEN_DATA
---

# _DOT4_DC_OPEN_DATA structure
This topic describes the <b>DOT4_DC_OPEN_DATA</b> structure.

## Syntax
````
typedef struct _DOT4_DC_OPEN_DATA {
  unsigned char  bHsid;
  fAddActivity   unsigned char;
  CHANNEL_HANDLE hChannelHandle;
} DOT4_DC_OPEN_DATA, *PDOT4_DC_OPEN_DATA;
````

## Members


`bHsid`

Specifies the host socket created by CREATE_SOCKET.

`fAddActivity`



`hChannelHandle`

Specifies the handle to the channel returned.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d4drvif.h |