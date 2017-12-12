---
UID: NC.ndis.FILTER_ATTACH
title: FILTER_ATTACH
author: windows-driver-content
description: NDIS calls a filter driver's FilterAttach function to allocate and initialize a filter module's data structures.Note  You must declare the function by using the FILTER_ATTACH type.
old-location: netvista\filterattach.htm
old-project: netvista
ms.assetid: 0a15a8c9-74af-4d93-bd12-a3c81c177684
ms.author: windowsdriverdev
ms.date: 12/8/2017
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
req.alt-api: FilterAttach
req.alt-loc: ndis.h
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

# FILTER_ATTACH callback



## -description
NDIS calls a filter driver's 
  <i>FilterAttach</i> function to allocate and initialize a filter module's data structures.



## -prototype

````
FILTER_ATTACH FilterAttach;

NDIS_STATUS FilterAttach(
  _In_ NDIS_HANDLE                    NdisFilterHandle,
  _In_ NDIS_HANDLE                    FilterDriverContext,
  _In_ PNDIS_FILTER_ATTACH_PARAMETERS AttachParameters
)
{ ... }
````


## -parameters

### -param NdisFilterHandle [in]

An NDIS handle that identifies a filter module. The filter driver must save this handle. The
     handle is required in subsequent calls to 
     <b>NdisF<i>Xxx</i></b> functions.


### -param FilterDriverContext [in]

The handle that the driver passed to the 
     <a href="netvista.ndisfregisterfilterdriver">
     NdisFRegisterFilterDriver</a> function that identifies the driver context area.


### -param AttachParameters [in]

A pointer to an 
     <a href="netvista.ndis_filter_attach_parameters">
     NDIS_FILTER_ATTACH_PARAMETERS</a> structure that defines the initialization parameters for the filter
     module.


## -returns
<i>FilterAttach</i> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><i>FilterAttach</i> successfully allocated and initialized data structures for this filter
       module.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><i>FilterAttach</i> failed because of insufficient resources.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl><i>FilterAttach</i> returns NDIS_STATUS_FAILURE if none of the preceding values applies. The filter
       driver should call the 
       <a href="netvista.ndiswriteeventlogentry">NdisWriteEventLogEntry</a> function
       together with parameters that specify the reason for the failure.

 


## -remarks
<i>FilterAttach</i> is a required function. NDIS calls a filter driver's 
    <i>FilterAttach</i> function when the specified filter module is in the 
    <i>Detached</i> state. NDIS can call 
    <i>FilterAttach</i> at any time after the call to the 
    <a href="netvista.filtersetoptions">FilterSetOptions</a> function returns.

At the start of execution in 
    <i>FilterAttach</i>, the filter module enters the 
    <i>Attaching</i> state.

Filter drivers should avoid issuing unnecessary OID queries. Instead, use the information in 
    <a href="netvista.ndis_filter_attach_parameters">
    NDIS_FILTER_ATTACH_PARAMETERS</a>, when available, to obtain information about underlying drivers.

A filter driver performs the following operations when NDIS calls 
    <i>FilterAttach</i>.

Creates a context area for the filter module and allocates buffer pools and any other resources.

Calls the 
      <a href="netvista.ndisfsetattributes">NdisFSetAttributes</a> function together
      with the 
      <i>NdisFilterHandle</i> that NDIS passed to 
      <i>FilterAttach</i>. The 
      <i>FilterModuleContext</i> parameter of 
      <b>NdisFSetAttributes</b> specifies the filter driver's context area for this filter module. NDIS passes
      this context area to the filter driver's 
      <i>FilterXxx</i> functions.

Optionally reads configuration parameters from the registry.

If the preceding operations completed successfully, the filter module enters the 
      <i>Paused</i> state.

If the preceding operations failed, the filter driver must release any resources that it allocated
      in the 
      <i>FilterAttach</i> function and return the filter module to the 
      <i>Detached</i> state.

Returns NDIS_STATUS_SUCCESS or an appropriate failure code.

A filter driver should not make send requests, indicate received data, make OID requests, or make
    status indications from the 
    <i>Attaching</i> state.

NDIS calls a filter driver's 
    <a href="..\ndis\nc-ndis-filter_detach.md">FilterDetach</a> function to release all the
    resources that are associated with a filter module and return the filter module to the 
    <i>Detached</i> state.

NDIS calls 
    <i>FilterAttach</i> at IRQL = PASSIVE_LEVEL.

To define a <i>FilterAttach</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterAttach</i> function that is named "MyAttach", use the <b>FILTER_ATTACH</b> type as shown in this code example:

Then, implement your function as follows:

The <b>FILTER_ATTACH</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_ATTACH</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

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
<a href="..\ndis\nc-ndis-filter_detach.md">FilterDetach</a>
</dt>
<dt>
<a href="netvista.filtersetoptions">FilterSetOptions</a>
</dt>
<dt>
<a href="netvista.ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="netvista.ndisfsetattributes">NdisFSetAttributes</a>
</dt>
<dt>
<a href="netvista.ndiswriteeventlogentry">NdisWriteEventLogEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_ATTACH callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

