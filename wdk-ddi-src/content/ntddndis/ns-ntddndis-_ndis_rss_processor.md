---
UID : NS:ntddndis._NDIS_RSS_PROCESSOR
title : "_NDIS_RSS_PROCESSOR"
author : windows-driver-content
description : The NDIS_RSS_PROCESSOR structure specifies information about a processor in the local computer for receive side scaling (RSS).
old-location : netvista\ndis_rss_processor.htm
old-project : netvista
ms.assetid : 4d823303-01ec-4587-a11c-f641cfd7c10f
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NDIS_RSS_PROCESSOR, *PNDIS_RSS_PROCESSOR, NDIS_RSS_PROCESSOR structure [Network Drivers Starting with Windows Vista], netvista.ndis_rss_processor, ntddndis/PNDIS_RSS_PROCESSOR, PNDIS_RSS_PROCESSOR structure pointer [Network Drivers Starting with Windows Vista], ndis_processor_group_ref_cbab90a4-91cf-4df3-a9dc-94f3cacf2039.xml, ntddndis/NDIS_RSS_PROCESSOR, _NDIS_RSS_PROCESSOR, PNDIS_RSS_PROCESSOR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.20 and later.
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_RSS_PROCESSOR, *PNDIS_RSS_PROCESSOR
---

# _NDIS_RSS_PROCESSOR structure
The NDIS_RSS_PROCESSOR structure specifies information about a processor in the local computer for
  receive side scaling (RSS).

## Syntax
````
typedef struct _NDIS_RSS_PROCESSOR {
  PROCESSOR_NUMBER ProcNum;
  USHORT           PreferenceIndex;
  USHORT           Reserved;
} NDIS_RSS_PROCESSOR, *PNDIS_RSS_PROCESSOR;
````

## Members


`PreferenceIndex`

The preference rating of the processor, which is based on Non-Uniform Memory Access (NUMA) distance.
      A lower value for 
      <b>PreferenceIndex</b> indicates a smaller NUMA distance to the miniport
      driver.

When choosing between multiple processors, miniport drivers should select the processor with a lower
      
      <b>PreferenceIndex</b> value. This results in less overhead for the driver.

`ProcNum`

The processor number that is assigned to the processor.

`Reserved`

Reserved for NDIS.

## Remarks
The NDIS_RSS_PROCESSOR structure is used in the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_rss_processor_info.md">
    NDIS_RSS_PROCESSOR_INFO</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_rss_processor_info.md">NDIS_RSS_PROCESSOR_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RSS_PROCESSOR structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>