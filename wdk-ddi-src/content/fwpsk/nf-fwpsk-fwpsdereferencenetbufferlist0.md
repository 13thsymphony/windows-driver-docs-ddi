---
UID: NF:fwpsk.FwpsDereferenceNetBufferList0
title: FwpsDereferenceNetBufferList0 function
author: windows-driver-content
description: The FwpsDereferenceNetBufferList0 function decrements the reference count for a NET_BUFFER_LIST structure that a callout driver had acquired earlier using the FwpsReferenceNetBufferList0 function.Note  FwpsDereferenceNetBufferList0 is a specific version of FwpsDereferenceNetBufferList. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsdereferencenetbufferlist0.htm
old-project: netvista
ms.assetid: e327fe9d-9425-4cc3-9552-88e9c4c3bdbe
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpsDereferenceNetBufferList0
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
req.alt-api: FwpsDereferenceNetBufferList0
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

# FwpsDereferenceNetBufferList0 function



## -description
The 
  <b>FwpsDereferenceNetBufferList0</b> function decrements the reference count for a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that a callout
  driver had acquired earlier using the 
  <a href="..\fwpsk\nf-fwpsk-fwpsreferencenetbufferlist0.md">FwpsReferenceNetBufferList0</a> function.



## -syntax

````
void NTAPI FwpsDereferenceNetBufferList0(
  _Inout_ NET_BUFFER_LIST *netBufferList,
  _In_    BOOLEAN         dispatchLevel
);
````


## -parameters

### -param netBufferList [in, out]

A pointer to the 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for which the
     reference count is being decremented.


### -param dispatchLevel [in]

A value that indicates that the current IRQL = DISPATCH_LEVEL. A callout driver should set this
     parameter to <b>TRUE</b> only if it is known that it is running at IRQL = DISPATCH_LEVEL. Otherwise a callout
     driver sets this parameter to <b>FALSE</b>.


## -returns
None.


## -remarks
A callout driver calls the 
    <b>FwpsDereferenceNetBufferList0</b> function to decrement the reference count for a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that it had
    acquired earlier using the 
    <a href="..\fwpsk\nf-fwpsk-fwpsreferencenetbufferlist0.md">FwpsReferenceNetBufferList0</a> function. A callout driver must not call the 
    <b>FwpsDereferenceNetBufferList0</b> function for a NET_BUFFER_LIST structure unless it previously called
    the 
    <b>
    FwpsReferenceNetBufferList0</b> for the same structure.


## -see-also
<dl>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsreferencenetbufferlist0.md">FwpsReferenceNetBufferList0</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsDereferenceNetBufferList0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

