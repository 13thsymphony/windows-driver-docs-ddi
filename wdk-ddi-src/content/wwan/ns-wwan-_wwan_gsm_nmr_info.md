---
UID : NS:wwan._WWAN_GSM_NMR_INFO
title : "_WWAN_GSM_NMR_INFO"
author : windows-driver-content
description : The WWAN_GSM_NMR_INFO structure represents information about a neighboring GSM cell.
old-location : netvista\wwan_gsm_nmr_info.htm
old-project : netvista
ms.assetid : EF22D5C3-7A3B-4A96-A050-FCB71CA2C149
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wwan/WWAN_GSM_NMR_INFO, wwan/PWWAN_GSM_NMR_INFO, PWWAN_GSM_NMR_INFO, WWAN_GSM_NMR_INFO structure [Network Drivers Starting with Windows Vista], netvista.wwan_gsm_nmr_info, _WWAN_GSM_NMR_INFO, WWAN_GSM_NMR_INFO, *PWWAN_GSM_NMR_INFO, PWWAN_GSM_NMR_INFO structure pointer [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wwan.h
req.include-header : Wwan.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1709
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
req.typenames : WWAN_GSM_NMR_INFO, *PWWAN_GSM_NMR_INFO
req.product : Windows 10 or later.
---

# _WWAN_GSM_NMR_INFO structure
The <b>WWAN_GSM_NMR_INFO</b> structure represents information about a neighboring GSM cell.

## Syntax
````
typedef struct _WWAN_GSM_NMR_INFO {
  ULONG ProviderIdOffset;
  ULONG ProviderIdSize;
  ULONG LocationAreaCode;
  ULONG CellId;
  ULONG ARFCN;
  ULONG BaseStationId;
  ULONG RxLevel;
  BYTE  Data[ANYSIZE_ARRAY];
} WWAN_GSM_NMR_INFO, *PWWAN_GSM_NMR_INFO;
````

## Members


`ARFCN`

The Absolute Radio Frequency Channel Number of the serving cell (0-1023). Use 0xFFFFFFFF when this information is not available.

`BaseStationId`

The radio Base Station ID of the serving cell (0-63). Use 0xFFFFFFFF when this information is not available.

`CellId`

The Cell ID (0-65535). Use 0xFFFFFFFF when this information is not available.

`Data`



`LocationAreaCode`

The Location Area Code (0-65535). Use 0xFFFFFFFF when this information is not available.

`ProviderIdOffset`

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called <i>ProviderId</i> that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no <i>ProviderId</i> information is returned.

`ProviderIdSize`

The size, in bytes, used for <i>ProviderId</i>.

`RxLevel`

The received signal strength (RSS) of the serving cell (0-63), where
<pre class="syntax" xml:space="preserve"><code>X = 0, if RSS &lt; -110 dBm</code></pre><pre class="syntax" xml:space="preserve"><code>X = 63, if RSS &gt; -47 dBm</code></pre><pre class="syntax" xml:space="preserve"><code>X = integer [RSS + 110], if -110 &lt;= RSS &lt;= -47</code></pre>Use 0xFFFFFFFF when this information is not available.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_gsm_serving_cell_info.md">WWAN_GSM_SERVING_CELL_INFO</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>

<a href="..\wwan\ns-wwan-_wwan_base_stations_info.md">WWAN_BASE_STATIONS_INFO</a>

<a href="..\wwan\ns-wwan-_wwan_gsm_nmr.md">WWAN_GSM_NMR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_GSM_NMR_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>