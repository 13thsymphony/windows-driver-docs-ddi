---
UID : NS:rilapitypes.RILC2KMRL
title : RILC2KMRL
author : windows-driver-content
description : This structure represents a RILC2KMRL.
old-location : netvista\rilc2kmrl.htm
old-project : netvista
ms.assetid : e2c289de-fff7-4e21-8ef5-2ff3006a4ea5
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILC2KMRL structure [Network Drivers Starting with Windows Vista], RILC2KMRL, netvista.rilc2kmrl, *LPRILC2KMRL, rilapitypes/RILC2KMRL
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : rilapitypes.h
req.include-header : Rilapitypes.h
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
req.typenames : RILC2KMRL, *LPRILC2KMRL
req.product : Windows 10 or later.
---

# RILC2KMRL structure
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILC2KMRL.

## Syntax
````
struct RILC2KMRL {
  DWORD dwParams;
  BOOL  fServing;
  DWORD dwNID;
  DWORD dwSID;
  DWORD dwBaseStationID;
  DWORD dwBaseLat;
  DWORD dwBaseLong;
  DWORD dwRefPN;
  DWORD dwGPSSeconds;
  DWORD dwPilotStrength;
};
````

## Members


`dwBaseLat`

Base station Latitude (0...4194303) encoded in units of 0.25 seconds, expressed in two’s complement representation within the low 22 bits of the DWORD. This is a signed field with North latitudes represented by positive values.

`dwBaseLong`

Base station Longitude (0...8388607) encoded in units of 0.25 seconds, expressed in two’s complement representation within the low 23 bits of the DWORD. This is a signed field with East longitudes represented by positive values.

`dwBaseStationID`

Base station ID (0...65535).

`dwGPSSeconds`

GPS seconds; the time at which this arrived from the base station.

`dwNID`

Network ID (0...65535).

`dwParams`

A bitwise combination of RILC2KMRLPARAMMASK enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

`dwPilotStrength`

Signal strength of pilot (0...63).

`dwRefPN`

Base station PN number (0...511).

`dwSID`

System ID (0...32767).

`fServing`

Indicates whether this is a serving cell. There may be more than one serving cell at a time.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILC2KMRL structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>