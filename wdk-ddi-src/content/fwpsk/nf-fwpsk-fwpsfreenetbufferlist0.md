---
UID: NF:fwpsk.FwpsFreeNetBufferList0
title: FwpsFreeNetBufferList0 function
author: windows-driver-content
description: The FwpsFreeNetBufferList0 function frees a NET_BUFFER_LIST structure that was previously allocated by a call to the FwpsAllocateNetBufferAndNetBufferList0 function.Note  FwpsFreeNetBufferList0 is a specific version of FwpsFreeNetBufferList.
old-location: netvista\fwpsfreenetbufferlist0.htm
old-project: netvista
ms.assetid: 7e337d7a-a408-4574-8da3-ea333fdbde8b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpsFreeNetBufferList0
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
req.alt-api: FwpsFreeNetBufferList0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsFreeNetBufferList0 function



## -description
The 
  <b>FwpsFreeNetBufferList0</b> function frees a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that was previously
  allocated by a call to the 
  <a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">FwpsAllocateNetBufferAndNetBufferList0</a> function.



## -syntax

````
void NTAPI FwpsFreeNetBufferList0(
  _Inout_ NET_BUFFER_LIST *netBufferList
);
````


## -parameters

### -param netBufferList [in, out]

A pointer to the 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that is being
     freed.


## -returns
None


## -remarks
A callout driver calls the 
    <b>FwpsFreeNetBufferList0</b> function to free a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that was
    previously allocated by a call to the 
    <a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">FwpsAllocateNetBufferAndNetBufferList0</a> function.


## -see-also
<dl>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">
   FwpsAllocateNetBufferAndNetBufferList0</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsFreeNetBufferList0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

