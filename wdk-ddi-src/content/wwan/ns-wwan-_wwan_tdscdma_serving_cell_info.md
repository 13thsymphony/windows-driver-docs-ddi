---
UID: NS:wwan._WWAN_TDSCDMA_SERVING_CELL_INFO
title: _WWAN_TDSCDMA_SERVING_CELL_INFO
author: windows-driver-content
description: The WWAN_TDSCDMA_SERVING_CELL_INFO structure represents information about the TDSCDMA serving cell.
old-location: netvista\wwan_tdscdma_serving_cell_info.htm
old-project: netvista
ms.assetid: 5D0DD219-8D81-4F72-B327-119A45CC35B4
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _WWAN_TDSCDMA_SERVING_CELL_INFO, WWAN_TDSCDMA_SERVING_CELL_INFO, *PWWAN_TDSCDMA_SERVING_CELL_INFO
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
req.alt-api: WWAN_TDSCDMA_SERVING_CELL_INFO
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
req.typenames: WWAN_TDSCDMA_SERVING_CELL_INFO, *PWWAN_TDSCDMA_SERVING_CELL_INFO
req.product: Windows 10 or later.
---

# _WWAN_TDSCDMA_SERVING_CELL_INFO structure



## -description
The <b>WWAN_TDSCDMA_SERVING_CELL_INFO</b> structure represents information about the TDSCDMA serving cell.



## -syntax

````
typedef struct _WWAN_TDSCDMA_SERVING_CELL_INFO {
  ULONG ProviderIdOffset;
  ULONG ProviderIdSize;
  ULONG LocationAreaCode;
  ULONG CellId;
  ULONG UARFCN;
  ULONG CellParameterID;
  ULONG TimingAdvance;
  ULONG RSCP;
  ULONG PathLoss;
  BYTE  Data[ANYSIZE_ARRAY];
} WWAN_TDSCDMA_SERVING_CELL_INFO, *PWWAN_TDSCDMA_SERVING_CELL_INFO;
````


## -struct-fields

### -field ProviderIdOffset

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called <i>ProviderId</i> that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no <i>ProviderId</i> information is returned.


### -field ProviderIdSize

The size, in bytes, used for <i>ProviderId</i>.


### -field LocationAreaCode

The Location Area Code (0-65535). Use 0xFFFFFFFF when this information is not available.


### -field CellId

The Cell ID (0-268435455). Use 0xFFFFFFFF when this information is not available.


### -field UARFCN

The UTRA Absolute Radio Frequency Channel Number for the serving cell (0-16383). Use 0xFFFFFFFF when this information is not available.


### -field CellParameterID

The Cell Parameter ID (0-127). Use 0xFFFFFFFF when this information is not available.


### -field TimingAdvance

The Timing Advance (0-1023). This member is the same value for all timeslots. Use 0xFFFFFFFF when this information is not available.


### -field RSCP

The Received Signal Code Power of the serving cell. The range is -120 to -25, in units of 1dBm in Q8 L3 filtered. Use 0xFFFFFFFF when this information is not available.


### -field PathLoss

The path loss of the serving cell (46-158). Use 0xFFFFFFFF when this information is not available.


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
<a href="..\wwan\ns-wwan-_wwan_base_stations_info.md">WWAN_BASE_STATIONS_INFO</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_tdscdma_mrl.md">WWAN_TDSCDMA_MRL</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_tdscdma_mrl_info.md">WWAN_TDSCDMA_MRL_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/200954a6-0f6c-4c00-86cb-510399f7b713">MB base stations information query support</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_TDSCDMA_SERVING_CELL_INFO structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

