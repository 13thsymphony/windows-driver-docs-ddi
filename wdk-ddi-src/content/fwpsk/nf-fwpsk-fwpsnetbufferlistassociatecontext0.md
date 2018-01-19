---
UID : NF:fwpsk.FwpsNetBufferListAssociateContext0
title : FwpsNetBufferListAssociateContext0 function
author : windows-driver-content
description : The FwpsNetBufferListAssociateContext0 function associates the callout driver's context with a network buffer list and configures notification for network buffer list events.Note  FwpsNetBufferListAssociateContext0 is the specific version of FwpsNetBufferListAssociateContext used in Windows 7 and later. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information. For Windows 8, FwpsNetBufferListAssociateContext1 is available.
old-location : netvista\fwpsnetbufferlistassociatecontext0.htm
old-project : netvista
ms.assetid : 31135396-303b-4b94-8616-a4b7be207fa1
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : FwpsNetBufferListAssociateContext0
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with  Windows 7.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FwpsNetBufferListAssociateContext0
req.alt-loc : fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Fwpkclnt.lib
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : FWPS_VSWITCH_EVENT_TYPE
---


# FwpsNetBufferListAssociateContext0 function
The 
  <b>FwpsNetBufferListAssociateContext0</b> function associates the callout driver's context with a network buffer
  list and configures notification for network buffer list events.

## Syntax

````
NTSTATUS NTAPI FwpsNetBufferListAssociateContext0(
  _Inout_ NET_BUFFER_LIST                 *netBufferList,
  _In_    UINT16                          layerId,
  _In_    UINT64                          context,
  _In_    UINT64                          contextTag,
  _In_    GUID                            *providerGUID,
  _Inout_ void                            *deviceObject,
  _In_    FWPS_NET_BUFFER_LIST_NOTIFY_FN0 notifyFn,
  _In_    UINT32                          flags
);
````

## Parameters

`netBufferList`

A network buffer list that indicates one or more packets of interest to the callout driver.

`layerId`

The identifier of the layer in which the context is being associated. When calling this function
     from the NDIS receive path, set this parameter to FWPS_LAYER_NON_WFP.

`context`

Arbitrary context information set by the callout driver. The filter engine will pass this context
     to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_net_buffer_list_notify_fn0.md">
     FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a>.

`contextTag`

A locally unique identifier obtained by calling the 
     <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistgettagforcontext0.md">
     FwpsNetBufferListGetTagForContext0</a> function.

`providerGuid`



`deviceObject`

A pointer to the callout driver's device object.

`notifyFn`

A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_net_buffer_list_notify_fn0.md">
     FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a> function. The filter engine will send status notifications to this
     function.

`flags`

This parameter is reserved for future use and is set to zero.


## Return Value

The 
     <b>FwpsNetBufferListAssociateContext0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The association was successful.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

## Remarks

The 
    <b>FwpsNetBufferListAssociateContext0</b> function associates groups of packets with the callout driver.
    Packets of interest can be tracked for inspection through multiple layers in the stack.

Before calling this function, the 
    <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistgettagforcontext0.md">FwpsNetBufferListGetTagForContext0</a> function must be called to obtain a context tag.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext1.md">FwpsNetBufferListAssociateContext1</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistgettagforcontext0.md">
   FwpsNetBufferListGetTagForContext0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistremovecontext0.md">
   FwpsNetBufferListRemoveContext0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistretrievecontext0.md">
   FwpsNetBufferListRetrieveContext0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/a151256b-d69f-4abb-bf68-644f157dfdd7">Using Packet Tagging</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsNetBufferListAssociateContext0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>