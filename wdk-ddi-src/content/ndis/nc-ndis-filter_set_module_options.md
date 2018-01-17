---
UID: NC:ndis.FILTER_SET_MODULE_OPTIONS
title: FILTER_SET_MODULE_OPTIONS function
author: windows-driver-content
description: The FilterSetModuleOptions function changes the set of optional services that are associated with a specified filter module.Note  You must declare the function by using the FILTER_SET_MODULE_OPTIONS type.
old-location: netvista\filtersetmoduleoptions.htm
old-project: netvista
ms.assetid: 04b7ac32-8996-4648-8c88-aa9f630b1bc4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FILTER_SET_MODULE_OPTIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: (*FILTER_SET_FILTER_MODULE_OPTIONS_HANDLER)
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
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# FILTER_SET_MODULE_OPTIONS function



## -description
The
  <i>FilterSetModuleOptions</i> function changes the set of optional services that are
  associated with a specified filter module.



## -syntax

````
FILTER_SET_MODULE_OPTIONS FilterSetModuleOptions;

NDIS_STATUS FilterSetModuleOptions(
  _In_ NDIS_HANDLE FilterModuleContext
)
{ ... }

typedef FILTER_SET_MODULE_OPTIONS (*FILTER_SET_FILTER_MODULE_OPTIONS_HANDLER);
````


## -parameters

### -param FilterModuleContext [in]

A handle to the context area for the filter module that is the target of this request. The filter
     driver created and initialized this context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


## -returns
<i>FilterSetModuleOptions</i> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><i>FilterSetModuleOptions</i> successfully registered the filter module's optional
       services and resources.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><i>FilterSetModuleOptions</i> could not allocate the resources that the filter
       module requires.
<dl>
<dt><b>NDIS_STATUS_
       <i>XXX</i> or NTSTATUS_
       <i>XXX</i></b></dt>
</dl>The filter driver's attempt to register options failed. Usually, such an error status is
       propagated from an 
       <b>Ndis<i>Xxx</i></b> function or a kernel-mode support routine.

 


## -remarks
If 
    <i>FilterSetModuleOptions</i> is defined, NDIS calls 
    <i>FilterSetModuleOptions</i> before it calls the 
    <a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a> function to start the
    filter module.

A filter driver specifies the default values for the changeable filter module options in the
    NDIS_FILTER_DRIVER_CHARACTERISTICS structure that it passes to the 
    <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> function during driver initialization.

To change options for a specific filter module at run time, the filter driver must also specify an
    entry point for 
    <i>FilterSetModuleOptions</i> in the 
    <a href="..\ndis\ns-ndis-_ndis_filter_driver_characteristics.md">
    NDIS_FILTER_DRIVER_CHARACTERISTICS</a> structure.

To specify the options that should be changed, 
    <i>FilterSetModuleOptions</i> defines a characteristics structure and calls the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function.
    Filter drivers must not call 
    <b>NdisSetOptionalHandlers</b> from a different thread.

The possible characteristics structures that can be specified from 
    <i>FilterSetModuleOptions</i> are:


<a href="..\ndis\ns-ndis-_ndis_filter_partial_characteristics.md">
       NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_client_chimney_offload_generic_characteristics.md">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_client_chimney_offload_tcp_characteristics.md">
       NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_provider_chimney_offload_generic_characteristics.md">
       NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_provider_chimney_offload_tcp_characteristics.md">
       NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS</a>


For information on the last four structures, see 
    <a href="netvista.full_tcp_offload">NDIS 6.0 TCP chimney offload
    documentation</a>.

The options that are specified in each characteristics structure can be different for each filter
    module.

When NDIS calls the 
    <i>FilterDetach</i> function, the filter driver should undo all the operations that
    were performed in 
    <i>FilterSetModuleOptions</i>.

NDIS calls 
    <i>FilterSetModuleOptions</i> at IRQL = PASSIVE_LEVEL.

To define a <i>FilterSetModuleOptions</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterSetModuleOptions</i> function that is named "MySetModuleOptions", use the <b>FILTER_SET_MODULE_OPTIONS</b> type as shown in this code example:

Then, implement your function as follows:

The <b>FILTER_SET_MODULE_OPTIONS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_SET_MODULE_OPTIONS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_filter_driver_characteristics.md">
   NDIS_FILTER_DRIVER_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_filter_partial_characteristics.md">
   NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_SET_MODULE_OPTIONS callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

