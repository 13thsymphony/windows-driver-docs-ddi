---
UID: NS.WWAN._WWAN_GSM_SERVING_CELL_INFO
title: _WWAN_GSM_SERVING_CELL_INFO
author: windows-driver-content
description: The WWAN_GSM_SERVING_CELL_INFO structure represents information about the GSM serving cell.
old-location: netvista\wwan_gsm_serving_cell_info.htm
old-project: netvista
ms.assetid: 37F6BD26-55F3-4E46-9C39-97A95B6FF5B1
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WWAN_GSM_SERVING_CELL_INFO, WWAN_GSM_SERVING_CELL_INFO, *PWWAN_GSM_SERVING_CELL_INFO
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
req.alt-api: WWAN_GSM_SERVING_CELL_INFO
req.alt-loc: wwan.h
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
req.product: Windows 10 or later.
---

# _WWAN_GSM_SERVING_CELL_INFO structure



## -description
The <b>WWAN_GSM_SERVING_CELL_INFO</b> structure represents information about the GSM serving cell.


## -syntax

````
typedef struct _WWAN_GSM_SERVING_CELL_INFO {
  ULONG ProviderIdOffset;
  ULONG ProviderIdSize;
  ULONG LocationAreaCode;
  ULONG CellId;
  ULONG TimingAdvance;
  ULONG ARFCN;
  ULONG BaseStationId;
  ULONG RxLevel;
  BYTE  Data[ANYSIZE_ARRAY];
} WWAN_GSM_SERVING_CELL_INFO, *PWWAN_GSM_SERVING_CELL_INFO;
````


## -struct-fields

### -field ProviderIdOffset

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called <i>ProviderId</i> that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no <i>ProviderId</i> information is returned.

### -field ProviderIdSize

The size, in bytes, used for <i>ProviderId</i>.

### -field LocationAreaCode

The Location Area Code (0-65535). Use 0xFFFFFFFF when this information is not available.

### -field CellId

The Cell ID (0-65535). Use 0xFFFFFFFF when this information is not available.

### -field TimingAdvance

The Timing Advance (0-255) in bit periods, where a bit period is 48/13µs. Use 0xFFFFFFFF when this information is not available.

### -field ARFCN

The Absolute Radio Frequency Channel Number of the serving cell (0-1023). Use 0xFFFFFFFF when this information is not available.

### -field BaseStationId

The Base Station ID - the base station color code and the network identity code. Use 0xFFFFFFFF when this information is not available.

### -field RxLevel

The received signal strength (RSS) of the serving cell (0-63), where
<pre class="syntax" xml:space="preserve"><code>X = 0, if RSS &lt; -110 dBm</code></pre>
<pre class="syntax" xml:space="preserve"><code>X = 63, if RSS &gt; -47 dBm</code></pre>
<pre class="syntax" xml:space="preserve"><code>X = integer [RSS + 110], if -110 &lt;= RSS &lt;= -47</code></pre>
Use 0xFFFFFFFF when this information is not available.

### -field Data[ANYSIZE_ARRAY]

The data buffer containing <i>ProviderId</i>.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Windows 10, version 1709
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.wwan_base_stations_info">WWAN_BASE_STATIONS_INFO</a>
</dt>
<dt>
<a href="netvista.wwan_gsm_nmr">WWAN_GSM_NMR</a>
</dt>
<dt>
<a href="netvista.wwan_gsm_nmr_info">WWAN_GSM_NMR_INFO</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_GSM_SERVING_CELL_INFO structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
