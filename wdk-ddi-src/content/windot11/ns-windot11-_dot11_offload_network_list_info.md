---
UID: NS.WINDOT11._DOT11_OFFLOAD_NETWORK_LIST_INFO
title: _DOT11_OFFLOAD_NETWORK_LIST_INFO
author: windows-driver-content
description: The DOT11_OFFLOAD_NETWORK_LIST_INFO structure describes a network offload-list (NLO).
old-location: netvista\dot11_offload_network_list_info.htm
old-project: NetVista
ms.assetid: 0FB1D72F-B183-408A-BB84-A9D54B6C276F
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _DOT11_OFFLOAD_NETWORK_LIST_INFO, PDOT11_OFFLOAD_NETWORK_LIST_INFO, *PDOT11_OFFLOAD_NETWORK_LIST_INFO, DOT11_OFFLOAD_NETWORK_LIST_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_OFFLOAD_NETWORK_LIST_INFO
req.alt-loc: Windot11.h
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

# _DOT11_OFFLOAD_NETWORK_LIST_INFO structure



## -description

## -syntax

````
typedef struct _DOT11_OFFLOAD_NETWORK_LIST_INFO {
  NDIS_OBJECT_HEADER    Header;
  ULONG                 ulFlags;
  ULONG                 FastScanPeriod;
  ULONG                 FastScanIterations;
  ULONG                 SlowScanPeriod;
  ULONG                 uNumOfEntries;
  DOT11_OFFLOAD_NETWORK offloadNetworkList[1];
} DOT11_OFFLOAD_NETWORK_LIST_INFO, *PDOT11_OFFLOAD_NETWORK_LIST_INFO;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_OFFLOAD_NETWORK_LIST_INFO structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_OFFLOAD_NETWORK_LIST_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_OFFLOAD_NETWORK_LIST_INFO_REVISION_1</td>
</tr>
</table>
 


### -field ulFlags

Bit flags to specify extra attributes of this NLO from the following table:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>DOT11_NLO_FLAG_STOP_NLO_INDICATION</td>
<td>Specifies that NLO scan should be stopped right away. No more NLO scans should occur. Nor should NLO discovery be indicated.  <b>uNumOfEntries</b>  should be 0.</td>
</tr>
<tr>
<td>DOT11_NLO_FLAG_SCAN_ON_AOAC_PLATFORM</td>
<td>Specifies that NLO should scan immediately, and the schedule of fast scan and slow scan should be followed. This is normally used on Always-On-Always-Connected (AOAC) platforms. <b>uNumOfEntries</b> can be from 0 to <i>n</i>.</td>
</tr>
<tr>
<td>DOT11_NLO_FLAG_SCAN_AT_SYSTEM_RESUME </td>
<td>Specifies that NLO is meant to be used at system resume on non-AOAC platfroms, which is never the case for AOAC platforms.  The NLO OID may be sent beforehand, when the systems is being suspended. Miniport/hardware should not start NLO scan right away. The list should be kept in miniport driver or hardware. When the system resumes, the miniport/hardware should try to connect to the previous connected network. The list should be scan right after the effort failed or when there is no previous connected AP to reconnect to.</td>
</tr>
</table>
 


### -field FastScanPeriod

Fast scan period, in seconds. When the NIC receives the offload list, it should scan for matches to the list within the <b>FastScanPeriod</b> interval. In the fast scan period, the NIC scans for interesting SSIDs every such period for <b>FastScanIteration</b> then it switches to <b>SlowScanPeriod</b>.


### -field FastScanIterations

Number if iterations to repeat the fast scan. When the number of iterations is reached the  NIC switches to the <b>SlowScanPeriod</b>.


### -field SlowScanPeriod

Slow scan period, in seconds.   After the <b>FastScanPeriod</b> expires, the NIC switch to the <b>SlowScanPeriod</b>.  The NIC should scan for matches to the list within the <b>SlowScanPeriod</b>.  The duration is open ended until Windows issues an updated  offload-list.


### -field uNumOfEntries

Number of networks in the list of those requested to offload.


### -field offloadNetworkList[1]

Array of networks that hardware should automatically search for.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows 8

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Windot11.h)</dt>
</dl>
</td>
</tr>
</table>