---
UID: NS:wwan._WWAN_UMTS_MRL_INFO
title: "_WWAN_UMTS_MRL_INFO"
author: windows-driver-content
description: The WWAN_UMTS_MRL_INFO structure represents information about a neighboring UMTS cell.
old-location: netvista\wwan_umts_mrl_info.htm
old-project: netvista
ms.assetid: C1129291-D0E7-48F6-B317-1A0BCB6D25DC
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_UMTS_MRL_INFO, PWWAN_UMTS_MRL_INFO, PWWAN_UMTS_MRL_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_UMTS_MRL_INFO, WWAN_UMTS_MRL_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_UMTS_MRL_INFO, netvista.wwan_umts_mrl_info, wwan/PWWAN_UMTS_MRL_INFO, wwan/WWAN_UMTS_MRL_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_UMTS_MRL_INFO
product: Windows
targetos: Windows
req.typenames: WWAN_UMTS_MRL_INFO, *PWWAN_UMTS_MRL_INFO
req.product: Windows 10 or later.
---

# _WWAN_UMTS_MRL_INFO structure
The <b>WWAN_UMTS_MRL_INFO</b> structure represents information about a neighboring UMTS cell.

## Syntax
```
typedef struct _WWAN_UMTS_MRL_INFO {
  ULONG ProviderIdOffset;
  ULONG ProviderIdSize;
  ULONG LocationAreaCode;
  ULONG CellId;
  ULONG UARFCN;
  ULONG PrimaryScramblingCode;
  ULONG RSCP;
  ULONG ECNO;
  ULONG PathLoss;
  BYTE  Data[ANYSIZE_ARRAY];
} WWAN_UMTS_MRL_INFO, *PWWAN_UMTS_MRL_INFO;
```

## Members


`ProviderIdOffset`

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called <i>ProviderId</i> that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no <i>ProviderId</i> information is returned.

`ProviderIdSize`

The size, in bytes, used for <i>ProviderId</i>.

`LocationAreaCode`

The Location Area Code (0-65535). Use 0xFFFFFFFF when this information is not available.

`CellId`

The Cell ID (0-268435455). Use 0xFFFFFFFF when this information is not available.

`UARFCN`

The UTRA Absolute Radio Frequency Channel Number for the serving cell (0-16383). Use 0xFFFFFFFF when this information is not available.

`PrimaryScramblingCode`

The Primary Scrambling Code of the serving cell (0-511). Use 0xFFFFFFFF when this information is not available.

`RSCP`

The Received Signal Code Power of the serving cell. The range is -120 to -25, in units of 1dBm. Use 0xFFFFFFFF when this information is not available.

`ECNO`

The signal to noise ratio of the serving cell; the ratio of the received energy per PN chip for the CPICH to the total received. The range is -50 to 0, in units of 1dBm. Use 1 when this information is not available.

`PathLoss`

The path loss of the serving cell (46-173). Use 0xFFFFFFFF when this information is not available.

`Data`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://msdn.microsoft.com/66460B28-C2B4-4F05-A133-31A753AF9489">WWAN_BASE_STATIONS_INFO</a>



<a href="https://msdn.microsoft.com/B62F63EB-747A-4672-9A79-5065A8BC04D1">WWAN_UMTS_MRL</a>



<a href="https://msdn.microsoft.com/62257D65-DCB9-43C3-A862-DAB31C27EF0A">WWAN_UMTS_SERVING_CELL_INFO</a>