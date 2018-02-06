---
UID: NF:fwpsk.FwpsDiscardClonedStreamData0
title: FwpsDiscardClonedStreamData0 function
author: windows-driver-content
description: The FwpsDiscardClonedStreamData0 function frees the memory buffer that is allocated by the FwpsCloneStreamData0 function.Note  FwpsDiscardClonedStreamData0 is a specific version of FwpsDiscardClonedStreamData.
old-location: netvista\fwpsdiscardclonedstreamdata0.htm
old-project: netvista
ms.assetid: 11e8338d-4ca3-49a4-8cfe-ac9f15434b4f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: fwpsk/FwpsDiscardClonedStreamData0, FwpsDiscardClonedStreamData0, FwpsDiscardClonedStreamData0 function [Network Drivers Starting with Windows Vista], netvista.fwpsdiscardclonedstreamdata0, wfp_ref_2_funct_3_fwps_D-H_b09851bf-8f28-4f16-8c7d-b6f89b276845.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsDiscardClonedStreamData0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---


# FwpsDiscardClonedStreamData0 function
The 
  <b>FwpsDiscardClonedStreamData0</b> function frees the memory buffer that is allocated by the 
  <a href="..\fwpsk\nf-fwpsk-fwpsclonestreamdata0.md">FwpsCloneStreamData0</a> function.
<div class="alert"><b>Note</b>  <b>FwpsDiscardClonedStreamData0</b> is a specific version of <b>FwpsDiscardClonedStreamData</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

````
void NTAPI FwpsDiscardClonedStreamData0(
  _Inout_ NET_BUFFER_LIST *netBufferListChain,
  _In_    UINT32          flags,
  _In_    BOOLEAN         dispatchLevel
);
````

## Parameters

`netBufferListChain`

A pointer to the 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure chain that is
     being freed. This will be the same as the 
     <i>netBufferListChain</i> parameter of the 
     <a href="..\fwpsk\nf-fwpsk-fwpsclonestreamdata0.md">FwpsCloneStreamData0</a> function.

`allocateCloneFlags`

TBD

`dispatchLevel`

A value that indicates the current IRQL = DISPATCH_LEVEL. A callout driver should set this
     parameter to <b>TRUE</b> only if it is running at IRQL = DISPATCH_LEVEL. Otherwise, a callout driver should set
     this parameter to <b>FALSE</b>.


## Return Value

None.

## Remarks

This function can be called when a cloned 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain is to be discarded
    instead of being reinjected back into the data stream.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista. Available starting with Windows Vista. |
| **Target Platform** | Universal |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** | Fwpkclnt.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\fwpsk\nf-fwpsk-fwpsclonestreamdata0.md">FwpsCloneStreamData0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsDiscardClonedStreamData0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>