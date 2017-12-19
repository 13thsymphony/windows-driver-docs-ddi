---
UID: NC.ndis.FILTER_PAUSE
title: FILTER_PAUSE
author: windows-driver-content
description: NDIS calls a filter driver's FilterPause function to initiate a pause operation for the specified filter module.Note  You must declare the function by using the FILTER_PAUSE type.
old-location: netvista\filterpause.htm
old-project: NetVista
ms.assetid: a239889e-ec39-48fc-9e82-c8bc3d7ca51a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FilterPause
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# FILTER_PAUSE callback



## -description
NDIS calls a filter driver's 
  <i>FilterPause</i> function to initiate a pause operation for the specified filter module.



## -prototype

````
FILTER_PAUSE FilterPause;

NDIS_STATUS FilterPause(
  _In_ NDIS_HANDLE                   FilterModuleContext,
  _In_ PNDIS_FILTER_PAUSE_PARAMETERS FilterPauseParameters
)
{ ... }
````


## -parameters

### -param FilterModuleContext [in]

A handle to the context area for the filter module that the filter driver should pause. The filter
     driver created and initialized this context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param FilterPauseParameters [in]

A pointer to an 
     <a href="netvista.ndis_filter_pause_parameters">
     NDIS_FILTER_PAUSE_PARAMETERS</a> structure that defines the pause parameters for the filter
     module.


## -returns
NDIS drivers cannot fail a pause request. The filter driver should call the 
     <a href="netvista.ndiswriteeventlogentry">NdisWriteEventLogEntry</a> function
     together with parameters that specify the reason for any errors that occur.
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><i>FilterPause</i> successfully paused the specified filter module.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>The filter driver will complete the request asynchronously with a call to the 
       <a href="netvista.ndisfpausecomplete">NdisFPauseComplete</a> function.

 


## -remarks
<i>FilterPause</i> is a required function. NDIS can call 
    <i>FilterPause</i> when the filter module is in the 
    <i>Running</i> state. The filter module enters the 
    <i>Pausing</i> state at the start of execution in the 
    <i>FilterPause</i> function.

A filter driver performs the following operations when NDIS calls 
    <i>FilterPause</i>:

Must call the 
      <a href="netvista.ndisfsendnetbufferlistscomplete">
      NdisFSendNetBufferListsComplete</a> function for any queued send buffers that an overlying driver
      created.

Must call the 
      <a href="netvista.ndisfreturnnetbufferlists">
      NdisFReturnNetBufferLists</a> function for any queued receive buffers that an underlying driver
      created.

Must wait for NDIS to return all outstanding send requests that the driver originated to the 
      <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
      FilterSendNetBufferListsComplete</a> function.

Must wait for NDIS to return all outstanding receive indications that the driver originated to the 
      <a href="..\ndis\nc-ndis-filter_return_net_buffer_lists.md">
      FilterReturnNetBufferLists</a> function.

After the filter driver returns NDIS_STATUS_SUCCESS from 
    <i>FilterPause</i> or calls the 
    <a href="netvista.ndisfpausecomplete">NdisFPauseComplete</a> function, the pause
    operation is complete. The filter module is in the 
    <i>Paused</i> state.

In the 
    <i>Pausing</i> or 
    <i>Paused</i> states, a filter driver should continue to handle OID requests or status indications. The
    driver should reject calls to its 
    <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">
    FilterSendNetBufferLists</a> function. The driver can pass on calls to its 
    <a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">
    FilterReceiveNetBufferLists</a> function. However, the driver cannot pass any buffers that it created.
    The driver must not originate any receive indications or send requests.

In the 
    <i>Paused</i> state, the filter module must not generate send requests or receive indications.

NDIS calls the 
    <a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a> function to initiate a
    restart request for a filter module that is in the 
    <i>Paused</i> state.

NDIS calls 
    <i>FilterPause</i> at IRQL = PASSIVE_LEVEL.

To define a <i>FilterPause</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterPause</i> function that is named "MyPause", use the <b>FILTER_PAUSE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>FILTER_PAUSE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_PAUSE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">FilterReceiveNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_return_net_buffer_lists.md">FilterReturnNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">FilterSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
   FilterSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="netvista.ndis_filter_pause_parameters">NDIS_FILTER_PAUSE_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndisfpausecomplete">NdisFPauseComplete</a>
</dt>
<dt>
<a href="netvista.ndisfreturnnetbufferlists">NdisFReturnNetBufferLists</a>
</dt>
<dt>
<a href="netvista.ndisfsendnetbufferlistscomplete">
   NdisFSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="netvista.ndiswriteeventlogentry">NdisWriteEventLogEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20FILTER_PAUSE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

