---
UID: NF:fwpsk.FwpsFreeCloneNetBufferList0
title: FwpsFreeCloneNetBufferList0 function
author: windows-driver-content
description: The FwpsFreeCloneNetBufferList0 function frees a clone NET_BUFFER_LIST structure that was previously allocated by a call to the FwpsAllocateCloneNetBufferList0 function.Note  FwpsFreeCloneNetBufferList0 is a specific version of FwpsFreeCloneNetBufferList. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsfreeclonenetbufferlist0.htm
old-project: netvista
ms.assetid: 0d0dea63-de0d-4421-b123-ce31ac6af1d9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FwpsFreeCloneNetBufferList0, FwpsFreeCloneNetBufferList0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsFreeCloneNetBufferList0, netvista.fwpsfreeclonenetbufferlist0, wfp_ref_2_funct_3_fwps_D-H_23efae1d-62cd-4559-b332-08ff843c3ab6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsFreeCloneNetBufferList0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---


# FwpsFreeCloneNetBufferList0 function
The 
  <b>FwpsFreeCloneNetBufferList0</b> function frees a clone 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that was previously
  allocated by a call to the 
  <a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">
  FwpsAllocateCloneNetBufferList0</a> function.
<div class="alert"><b>Note</b>  <b>FwpsFreeCloneNetBufferList0</b> is a specific version of <b>FwpsFreeCloneNetBufferList</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

````
void NTAPI FwpsFreeCloneNetBufferList0(
  _Inout_ NET_BUFFER_LIST *netBufferList,
  _In_    ULONG           freeCloneFlags
);
````

## Parameters

`netBufferList`

A pointer to the clone 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that is being
     freed.

`freeCloneFlags`

There are currently no flags defined for this function. Callout drivers should set this parameter
     to zero.


## Return Value

None.

## Remarks

A callout driver calls the 
    <b>FwpsFreeCloneNetBufferList0</b> function to free a clone 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that was
    previously allocated by a call to the 
    <a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">FwpsAllocateCloneNetBufferList0</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista.  |
| **Target Platform** | Universal |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** | Fwpkclnt.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">
   FwpsAllocateCloneNetBufferList0</a>