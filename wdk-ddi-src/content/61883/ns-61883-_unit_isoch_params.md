---
UID : NS:61883._UNIT_ISOCH_PARAMS
title : "_UNIT_ISOCH_PARAMS"
author : windows-driver-content
description : The UNIT_ISOCH_PARAMS structure is used to get or set the parameters that the IEC-61883 protocol driver uses when capturing or transmitting isochronous packets.
old-location : ieee\unit_isoch_params.htm
old-project : IEEE
ms.assetid : 1c661a35-8209-49c5-9987-b4b6e9e710b4
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : "*PUNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS structure [Buses], UNIT_ISOCH_PARAMS, 61883/PUNIT_ISOCH_PARAMS, 61883_structures_eece3eb1-516b-40a8-9529-e4a3d8832f02.xml, PUNIT_ISOCH_PARAMS, PUNIT_ISOCH_PARAMS structure pointer [Buses], IEEE.unit_isoch_params, _UNIT_ISOCH_PARAMS, 61883/UNIT_ISOCH_PARAMS"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : 61883.h
req.include-header : 61883.h
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
req.typenames : UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
---

# _UNIT_ISOCH_PARAMS structure
The UNIT_ISOCH_PARAMS structure is used to get or set the parameters that the IEC-61883 protocol driver uses when capturing or transmitting isochronous packets.

## Syntax
````
typedef struct _UNIT_ISOCH_PARAMS {
  ULONG RX_NumPackets;
  ULONG RX_NumDescriptors;
  ULONG TX_NumPackets;
  ULONG TX_NumDescriptors;
} UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS;
````

## Members


`RX_NumDescriptors`

The number of descriptors used for receiving isochronous data.

`RX_NumPackets`

The number of isochronous packets per descriptor to be received.

`TX_NumDescriptors`

The number of descriptors used for transmitting isochronous data.

`TX_NumPackets`

The number of isochronous packets per descriptor to be transmitted.

## Remarks
The UNIT_ISOCH_PARAMS structure can be used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a> to set the number of isochronous packets and descriptors used while transmitting or receiving data. Before setting isochronous parameters, a driver should send an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a> request to retrieve the current isochronous parameters and then make any necessary modifications with <b>Av61883_SetUnitInfo</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 61883.h (include 61883.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20UNIT_ISOCH_PARAMS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>