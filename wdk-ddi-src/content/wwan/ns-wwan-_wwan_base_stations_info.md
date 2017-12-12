---
UID: NS.WWAN._WWAN_BASE_STATIONS_INFO
title: _WWAN_BASE_STATIONS_INFO
author: windows-driver-content
description: The WWAN_BASE_STATIONS_INFO structure represents information about both serving and neighboring base stations.
old-location: netvista\wwan_base_stations_info.htm
old-project: netvista
ms.assetid: 66460B28-C2B4-4F05-A133-31A753AF9489
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WWAN_BASE_STATIONS_INFO, *PWWAN_BASE_STATIONS_INFO, WWAN_BASE_STATIONS_INFO
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
req.alt-api: WWAN_BASE_STATIONS_INFO
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

# _WWAN_BASE_STATIONS_INFO structure



## -description
The <b>WWAN_BASE_STATIONS_INFO</b> structure represents information about both serving and neighboring base stations.



## -syntax

````
typedef struct _WWAN_BASE_STATIONS_INFO {
  ULONG SystemType;
  ULONG GSMServingCellOffset;
  ULONG GSMServingCellSize;
  ULONG UMTSServingCellOffset;
  ULONG UMTSServingCellSize;
  ULONG TDSCDMAServingCellOffset;
  ULONG TDSCDMAServingCellSize;
  ULONG LTEServingCellOffset;
  ULONG LTEServingCellSize;
  ULONG GSMNmrOffset;
  ULONG GSMNmrSize;
  ULONG UMTSMrlOffset;
  ULONG UMTSMrlSize;
  ULONG TDSCDMAMrlOffset;
  ULONG TDSCDMAMrlSize;
  ULONG LTEMrlOffset;
  ULONG LTEMrlSize;
  ULONG CDMAMrlOffset;
  ULONG CDMAMrlSize;
  BYTE  BaseStationsData[ANYSIZE_ARRAY];
} WWAN_BASE_STATIONS_INFO, *PWWAN_BASE_STATIONS_INFO;
````


## -struct-fields

### -field SystemType

Indicates the system type (or types) for which serving cell information is valid. This member is a bitmask of one or more system types as defined in the <b>WwanDataClass</b> member of <a href="netvista.wwan_device_caps">WWAN_DEVICE_CAPS</a>.


### -field GSMServingCellOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the GSM serving cell information. This member can be NULL when the technology of the serving cell is not GSM.


### -field GSMServingCellSize

The size, in bytes, used for the buffer containing the GSM serving cell info, which is formatted as <a href="netvista.wwan_gsm_serving_cell_info">WWAN_GSM_SERVING_CELL_INFO</a>.


### -field UMTSServingCellOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the UMTS serving cell information. This member can be NULL when the technology of serving cell is not UMTS.


### -field UMTSServingCellSize

The size, in bytes, used for the buffer containing the UMTS serving cell info, which is formatted as <a href="netvista.wwan_umts_serving_cell_info">WWAN_UMTS_SERVING_CELL_INFO</a>.


### -field TDSCDMAServingCellOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the TDSCDMA serving cell information. This member can be NULL when the technology of serving cell is not TDSCDMA.


### -field TDSCDMAServingCellSize

The size, in bytes, used for the buffer containing the TDSCDMA serving cell info, which is formatted as <a href="netvista.wwan_tdscdma_serving_cell_info">WWAN_TDSCDMA_SERVING_CELL_INFO</a>.


### -field LTEServingCellOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the LTE serving cell information. This member can be NULL when the technology of serving cell is not LTE.


### -field LTEServingCellSize

The size, in bytes, used for the buffer containing the LTE serving cell info, which is formatted as <a href="netvista.wwan_lte_serving_cell_info">WWAN_LTE_SERVING_CELL_INFO</a>.


### -field GSMNmrOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the GSM network measurement report. This member can be NULL when no GSM neighboring network is returned in the measurement report.


### -field GSMNmrSize

The size, in bytes, of the buffer containing the GSM network measurement report (NMR), which is formatted as <a href="netvista.wwan_gsm_nmr">WWAN_GSM_NMR</a>.


### -field UMTSMrlOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing UMTS measured results list. This member can be NULL when no UMTS neighboring network is returned in the measurement report.


### -field UMTSMrlSize

The size, in bytes, of the buffer containing the UMTS measured results list (MRL), which is formatted as <a href="netvista.wwan_umts_mrl">WWAN_UMTS_MRL</a>.


### -field TDSCDMAMrlOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing TDSCDMA measured results list. This member can be NULL when no TDSCDMA neighboring network is returned in the measurement report.


### -field TDSCDMAMrlSize

The size, in bytes, of the buffer containing the TDSCDMA measured results list (MRL), which is formatted as <a href="netvista.wwan_tdscdma_mrl">WWAN_TDSCDMA_MRL</a>.


### -field LTEMrlOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing LTE measured results list. This member can be NULL when no LTE neighboring network is returned in the measurement report.


### -field LTEMrlSize

The size, in bytes, of the buffer containing the LTE measured results list (MRL), which is formatted as <a href="netvista.wwan_lte_mrl">WWAN_LTE_MRL</a>.


### -field CDMAMrlOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing CDMA measured results list. This member can be NULL when no CDMA neighboring network is returned in the measurement report.


### -field CDMAMrlSize

The size, in bytes, of the buffer containing the CDMA measured results list (MRL), which is formatted as <a href="netvista.wwan_cdma_mrl">WWAN_CDMA_MRL</a>.


### -field BaseStationsData[ANYSIZE_ARRAY]

The data buffer containing the base stations information. This buffer is where the structures specified by the other members of <b>WWAN_BASE_STATIONS_INFO</b> reside: <b>WWAN_GSM_SERVING_CELL_INFO</b>, <b>WWAN_UMTS_SERVING_CELL_INFO</b>, <b>WWAN_TDSCDMA_SERVING_CELL_INFO</b>, <b>WWAN_LTE_SERVING_CELL_INFO</b>, <b>WWAN_GSM_NMR</b>, <b>WWAN_UMTS_MRL</b>, <b>WWAN_TDSCDMA_MRL</b>, <b>WWAN_LTE_MRL</b>, and <b>WWAN_CDMA_MRL</b>.


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
<a href="netvista.ndis_wwan_base_stations_info">NDIS_WWAN_BASE_STATIONS_INFO</a>
</dt>
<dt>
<a href="netvista.wwan_device_caps">WWAN_DEVICE_CAPS</a>
</dt>
<dt>
<a href="netvista.wwan_gsm_serving_cell_info">WWAN_GSM_SERVING_CELL_INFO</a>
</dt>
<dt>
<a href="netvista.wwan_umts_serving_cell_info">WWAN_UMTS_SERVING_CELL_INFO</a>
</dt>
<dt>
<a href="netvista.wwan_tdscdma_serving_cell_info">WWAN_TDSCDMA_SERVING_CELL_INFO</a>
</dt>
<dt>
<a href="netvista.wwan_lte_serving_cell_info">WWAN_LTE_SERVING_CELL_INFO</a>
</dt>
<dt>
<a href="netvista.wwan_gsm_nmr">WWAN_GSM_NMR</a>
</dt>
<dt>
<a href="netvista.wwan_umts_mrl">WWAN_UMTS_MRL</a>
</dt>
<dt>
<a href="netvista.wwan_tdscdma_mrl">WWAN_TDSCDMA_MRL</a>
</dt>
<dt>
<a href="netvista.wwan_lte_mrl">WWAN_LTE_MRL</a>
</dt>
<dt>
<a href="netvista.wwan_cdma_mrl">WWAN_CDMA_MRL</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_BASE_STATIONS_INFO structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

