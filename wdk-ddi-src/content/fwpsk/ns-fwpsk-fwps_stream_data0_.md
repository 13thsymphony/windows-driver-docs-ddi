---
UID : NS:fwpsk.FWPS_STREAM_DATA0_
title : FWPS_STREAM_DATA0_
author : windows-driver-content
description : The FWPS_STREAM_DATA0 structure describes a portion of a data stream.Note  FWPS_STREAM_DATA0 is a specific version of FWPS_STREAM_DATA.
old-location : netvista\fwps_stream_data0.htm
old-project : netvista
ms.assetid : 7e9daf20-12d6-42dc-99fb-9e9efe5a9900
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : fwpsk/FWPS_STREAM_DATA0, FWPS_STREAM_DATA0 structure [Network Drivers Starting with Windows Vista], FWPS_STREAM_DATA0_, wfp_ref_3_struct_3_fwps_P-Z_d8d6e633-542c-4273-9341-935281133be4.xml, FWPS_STREAM_DATA0, netvista.fwps_stream_data0
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows Vista.
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
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : FWPS_STREAM_DATA0
---

# FWPS_STREAM_DATA0_ structure
The <b>FWPS_STREAM_DATA0</b> structure describes a portion of a data stream.
<div class="alert"><b>Note</b>  <b>FWPS_STREAM_DATA0</b> is a specific version of <b>FWPS_STREAM_DATA</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax
````
typedef struct FWPS_STREAM_DATA0_ {
  UINT32                   flags;
  FWPS_STREAM_DATA_OFFSET0 dataOffset;
  SIZE_T                   dataLength;
  NET_BUFFER_LIST          *netBufferListChain;
} FWPS_STREAM_DATA0;
````

## Members


`dataLength`

The number of bytes in the portion of the data stream.

`dataOffset`

An 
     <a href="..\fwpsk\ns-fwpsk-fwps_stream_data_offset0_.md">FWPS_STREAM_DATA_OFFSET0</a> structure
     that specifies the offset into the data stream where the portion of the data stream begins.

`flags`

A variable containing flags that specify the characteristics of the data stream.
     

For inbound data streams, this can be one or more of the following flags:



For outbound data streams, this can be one or more of the following flags:

`netBufferListChain`

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that describes
     the portion of the data stream.

## Remarks
The filter engine uses the FWPS_STREAM_DATA0 structure to describe the portion of a data stream that a
    callout's 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function can process. The 
    <b>dataStream</b> member of the 
    <mshelp:link keywords="netvista.fwps_stream_callout_io_packet0" tabindex="0"><b>
    FWPS_STREAM_CALLOUT_IO_PACKET0</b></mshelp:link> structure points to an FWPS_STREAM_DATA0 structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |

## See Also

<a href="..\fwpsk\ns-fwpsk-fwps_stream_data_offset0_.md">FWPS_STREAM_DATA_OFFSET0</a>

<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<mshelp:link keywords="netvista.fwps_stream_callout_io_packet0" tabindex="0"><b>
   FWPS_STREAM_CALLOUT_IO_PACKET0</b></mshelp:link>

<a href="..\fwpsk\nf-fwpsk-fwpsstreaminjectasync0.md">FwpsStreamInjectAsync0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_STREAM_DATA0 structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>