---
UID: NS:fwpsk.FWPS_PACKET_LIST_FWP_INFORMATION0_
title: FWPS_PACKET_LIST_FWP_INFORMATION0_
author: windows-driver-content
description: The FWPS_PACKET_LIST_FWP_INFORMATION0 structure defines Windows Filtering Platform information associated with a packet list.Note  FWPS_PACKET_LIST_FWP_INFORMATION0 is a specific version of FWPS_PACKET_LIST_FWP_INFORMATION.
old-location: netvista\fwps_packet_list_fwp_information0.htm
old-project: netvista
ms.assetid: e2d3faf3-cd3b-4147-8ceb-5b3f0c257939
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FWPS_PACKET_LIST_FWP_INFORMATION0, FWPS_PACKET_LIST_FWP_INFORMATION0 structure [Network Drivers Starting with Windows Vista], FWPS_PACKET_LIST_FWP_INFORMATION0_, fwpsk/FWPS_PACKET_LIST_FWP_INFORMATION0, netvista.fwps_packet_list_fwp_information0, wfp_ref_3_struct_3_fwps_P-Z_ae770ad6-5c74-4954-98ca-ffb23f8dcc7c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_PACKET_LIST_FWP_INFORMATION0
product: Windows
targetos: Windows
req.typenames: FWPS_PACKET_LIST_FWP_INFORMATION0
---

# FWPS_PACKET_LIST_FWP_INFORMATION0_ structure
The <b>FWPS_PACKET_LIST_FWP_INFORMATION0</b> structure defines Windows Filtering Platform information
  associated with a packet list.
<div class="alert"><b>Note</b>  <b>FWPS_PACKET_LIST_FWP_INFORMATION0</b> is a specific version of <b>FWPS_PACKET_LIST_FWP_INFORMATION</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax
````
typedef struct FWPS_PACKET_LIST_FWP_INFORMATION0_ {
  unsigned isReinjected  :1;
} FWPS_PACKET_LIST_FWP_INFORMATION0;
````

## Members


`isReinjected`

A value that indicates whether the packet data was reinjected by a callout driver.

## Remarks
A FWPS_PACKET_LIST_FWP_INFORMATION0 structure is included as a member of the 
    <a href="..\fwpsk\ns-fwpsk-fwps_packet_list_information0_.md">
    FWPS_PACKET_LIST_INFORMATION0</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista. Available starting with Windows Vista. |
| **Header** | fwpsk.h (include Fwpsk.h) |

## See Also

<a href="..\fwpsk\ns-fwpsk-fwps_packet_list_information0_.md">FWPS_PACKET_LIST_INFORMATION0</a>