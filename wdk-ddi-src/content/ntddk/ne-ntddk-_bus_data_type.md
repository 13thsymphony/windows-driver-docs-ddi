---
UID: NE.ntddk._BUS_DATA_TYPE
title: _BUS_DATA_TYPE
author: windows-driver-content
description: The BUS_DATA_TYPE enumeration indicates the type of bus configuration space.
old-location: kernel\bus_data_type.htm
old-project: kernel
ms.assetid: a2a2e964-b9ae-4367-85de-f0ebe3c7a952
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _BUS_DATA_TYPE, *PBUS_DATA_TYPE, BUS_DATA_TYPE, PBUS_DATA_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BUS_DATA_TYPE
req.alt-loc: Ntddk.h
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
---

# _BUS_DATA_TYPE enumeration



## -description
The <b>BUS_DATA_TYPE</b> enumeration indicates the type of bus configuration space.



## -syntax

````
typedef enum _BUS_DATA_TYPE { 
  ConfigurationSpaceUndefined  = -1,
  Cmos                         = 0,
  EisaConfiguration            = 1,
  Pos                          = 2,
  CbusConfiguration            = 3,
  PCIConfiguration             = 4,
  VMEConfiguration             = 5,
  NuBusConfiguration           = 6,
  PCMCIAConfiguration          = 7,
  MPIConfiguration             = 8,
  MPSAConfiguration            = 9,
  PNPISAConfiguration          = 10,
  SgiInternalConfiguration     = 11,
  MaximumBusDataType           = 12
} BUS_DATA_TYPE, *PBUS_DATA_TYPE;
````


## -enum-fields

### -field ConfigurationSpaceUndefined

Indicates that the type of bus configuration space is undefined.


### -field Cmos

Indicates CMOS data.


### -field EisaConfiguration

Indicates an EISA bus configuration space.


### -field Pos

For internal use only.


### -field CbusConfiguration

Indicates Cbus configuration space.


### -field PCIConfiguration

Indicates PCI configuration space.


### -field VMEConfiguration

Indicates VME configuration space.


### -field NuBusConfiguration

Indicates NuBus configuration space.


### -field PCMCIAConfiguration

Indicates PCMCIA configuration space.


### -field MPIConfiguration

Indicates MPI configuration space.


### -field MPSAConfiguration

Indicates MPSA configuration space.


### -field PNPISAConfiguration

Indicates PNPISA configuration space.


### -field SgiInternalConfiguration

Indicates SGI internal bus configuration space.


### -field MaximumBusDataType

Indicates the upper limit of the bus configuration space types.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546628">HalSetBusData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BUS_DATA_TYPE enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

