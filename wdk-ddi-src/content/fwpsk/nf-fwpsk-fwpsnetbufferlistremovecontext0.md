---
UID: NF.fwpsk.FwpsNetBufferListRemoveContext0
title: FwpsNetBufferListRemoveContext0 function
author: windows-driver-content
description: The FwpsNetBufferListRemoveContext0 function removes the context associated with a network buffer list.Note  FwpsNetBufferListRemoveContext0 is a specific version of FwpsNetBufferListRemoveContext.
old-location: netvista\fwpsnetbufferlistremovecontext0.htm
old-project: netvista
ms.assetid: bd3aa1a2-3ff5-47e4-93f6-5cb2022ec630
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: FwpsNetBufferListRemoveContext0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsNetBufferListRemoveContext0
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
---

# FwpsNetBufferListRemoveContext0 function



## -description
The 
  <b>FwpsNetBufferListRemoveContext0</b> function removes the context associated with a network buffer
  list.



## -syntax

````
NTSTATUS NTAPI FwpsNetBufferListRemoveContext0(
  _Inout_opt_ NET_BUFFER_LIST *netBufferList,
  _In_        UINT64          contextTag,
  _In_        UINT32          flags
);
````


## -parameters

### -param netBufferList [in, out, optional]

A network buffer list that indicates one or more packets of interest to the callout driver. This
     parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the function will remove the context from all associated network
     buffer lists.


### -param contextTag [in]

The context tag that was passed in the <i>contextTag</i> parameter to 
     <a href="netvista.fwpsnetbufferlistassociatecontext0">FwpsNetBufferListAssociateContext0</a>.


### -param flags [in]

This parameter is reserved for future use and must be zero.


## -returns
The 
     <b>FwpsNetBufferListRemoveContext0</b> function returns one of the following <b>NTSTATUS</b> codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The context was successfully removed.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
The 
    <b>FwpsNetBufferListRemoveContext0</b> function asynchronously removes the tagged context associated with a network buffer list.

To associate a context with a network buffer list, call 
    <a href="netvista.fwpsnetbufferlistassociatecontext0">
    FwpsNetBufferListAssociateContext0</a> or <a href="netvista.fwpsnetbufferlistassociatecontext1">FwpsNetBufferListAssociateContext1</a>.

Usually a callout driver will not need to use this function, because the tagged context
    is removed automatically when the packets move through the stack. This function is provided so that
    a callout driver can stop processing in situations where contexts aren't removed automatically. For example, in the case of an NDIS filter driver, the packets never enter the TCP/IP stack, and the contexts will need to be removed manually by calling <b>FwpsNetBufferListRemoveContext0</b> with the <i>netBufferList</i> parameter set to <b>NULL</b>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with  Windows 7.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Fwpkclnt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="netvista.fwpsnetbufferlistassociatecontext0">
   FwpsNetBufferListAssociateContext0</a>
</dt>
<dt>
<a href="netvista.fwpsnetbufferlistassociatecontext1">FwpsNetBufferListAssociateContext1</a>
</dt>
<dt>
<a href="netvista.fwpsnetbufferlistgettagforcontext0">
   FwpsNetBufferListGetTagForContext0</a>
</dt>
<dt>
<a href="netvista.fwpsnetbufferlistretrievecontext0">
   FwpsNetBufferListRetrieveContext0</a>
</dt>
<dt>
<a href="netvista.using_packet_tagging">Using Packet Tagging</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsNetBufferListRemoveContext0 function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

