---
UID : NC:ndis.FILTER_RESTART
title : FILTER_RESTART
author : windows-driver-content
description : The FilterRestart function initiates a restart operation for the specified filter module.Note  You must declare the function by using the FILTER_RESTART type.
old-location : netvista\filterrestart.htm
old-project : netvista
ms.assetid : 4a917824-eef1-4945-b45e-1c940bc8a50d
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RxNameCacheInitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FilterRestart
req.alt-loc : Ndis.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# FILTER_RESTART function
The 
  <i>FilterRestart</i> function initiates a restart operation for the specified filter module.

## Syntax

```
FILTER_RESTART FilterRestart;

NDIS_STATUS FilterRestart(
  NDIS_HANDLE FilterModuleContext,
  PNDIS_FILTER_RESTART_PARAMETERS RestartParameters
)
{...}
```

## Parameters

`FilterModuleContext`

A handle to the context area for the filter module that the filter driver should restart. The
     filter driver created and initialized this context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

`RestartParameters`




## Return Value

<i>FilterRestart</i> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><i>FilterRestart</i> successfully restarted the specified filter module.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>The filter driver will complete the request asynchronously with a call to the 
       <a href="..\ndis\nf-ndis-ndisfrestartcomplete.md">NdisFRestartComplete</a> function
       after it completes the restart operation.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><i>FilterRestart</i> failed because of insufficient resources.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>None of the preceding status values applies. The filter driver should call the 
       <a href="..\ndis\nf-ndis-ndiswriteeventlogentry.md">NdisWriteEventLogEntry</a> function
       together with parameters that specify the reason for the failure.

## Remarks

<i>FilterRestart</i> is a required function for filter drivers. NDIS can call 
    <i>FilterRestart</i> when a filter module is in the 
    <i>Paused</i> state. The filter module enters the 
    <i>Restarting</i> state at the start of the execution of 
    <i>FilterRestart</i>.

When NDIS calls 
    <i>FilterRestart</i>, a filter driver:

Must complete the operations that are required to restart normal send and receive operations.

Optionally reads or writes configuration parameters.

Optionally reallocates buffer pools.

Optionally modifies the restart attributes that are specified in the 
      <b>RestartAttributes</b> member of the 
      <a href="..\ndis\ns-ndis-_ndis_filter_restart_parameters.md">
      NDIS_FILTER_RESTART_PARAMETERS</a> structure. If the pointer in 
      <b>RestartAttributes</b> is <b>NULL</b>, the filter driver should not modify or add to the restart attributes
      list. If the pointer in 
      <b>RestartAttributes</b> is non-<b>NULL</b>, it points to the first 
      <a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a> structure
      in the list of restart attributes. If a filter driver does not restart, it should not modify any
      attributes.

Optionally uses OID requests to query or set information in the underlying drivers. Filter drivers
      should not issue OID requests for information that is already provided in the list of restart
      attributes.

Returns NDIS_STATUS_SUCCESS or a failure status.

If a filter driver modifies the list of restart attributes, the filter driver:

Should not modify any media-specific attributes if it does not recognize the OID in the 
      <b>Oid</b> member of the 
      <a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">
      NDIS_RESTART_ATTRIBUTES</a> structure.

Can add new media-specific attributes to the list of restart attributes. In this situation, the
      filter driver must allocate a new NDIS_RESTART_ATTRIBUTES structure--for example, with the 
      <a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">
      NdisAllocateMemoryWithTagPriority</a> function--and provide memory space for the new attributes.
      After propagating the restart attributes to overlying drivers, NDIS frees the attributes memory for
      filter drivers.

Can modify the media-specific attributes in the list of restart attributes. If the filter driver
      requires more memory space, it can free the 
      <a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a> structure
      with the 
      <a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a> function and allocate a
      new structure to contain the modified information. After propagating the restart attributes to
      overlying drivers, NDIS frees the attributes memory for filter drivers.

Should, if the 
      <b>Oid</b> member in the NDIS_RESTART_ATTRIBUTES structure is 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-miniport-restart-attributes">
      OID_GEN_MINIPORT_RESTART_ATTRIBUTES</a>, make sure that the 
      <a href="..\ndis\ns-ndis-_ndis_restart_general_attributes.md">
      NDIS_RESTART_GENERAL_ATTRIBUTES</a> structure contains the information that the filter driver
      requires. To make sure that the NDIS_RESTART_GENERAL_ATTRIBUTES structure contains the required
      information, you should check the 
      <b>Revision</b> member in the 
      <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure that is
      specified in the 
      <b>Header</b> member of the NDIS_RESTART_GENERAL_ATTRIBUTES structure.

Must, if the filter driver changes restart attributes, provide a 
      <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> function. The
      filter driver must make sure that the information that overlying drivers receive in the restart
      attributes is consistent with the information that they receive in response to OID requests.

After the filter driver returns its status or calls the 
    <a href="..\ndis\nf-ndis-ndisfrestartcomplete.md">NdisFRestartComplete</a> function, the
    restart operation is complete. If the operation completed successfully, the filter module is in the 
    <i>Running</i> state and normal send and receive processing is resumed. If the restart operation failed,
    the filter module returns to the 
    <i>Paused</i> state.

NDIS calls 
    <i>FilterRestart</i> at IRQL = PASSIVE_LEVEL.

To define a <i>FilterRestart</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterRestart</i> function that is named "MyRestart", use the <b>FILTER_RESTART</b> type as shown in this code example:

Then, implement your function as follows:

The <b>FILTER_RESTART</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_RESTART</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_status.md">FilterStatus</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_filter_restart_parameters.md">
   NDIS_FILTER_RESTART_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_restart_general_attributes.md">
   NDIS_RESTART_GENERAL_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567391">NDIS_STATUS_LINK_STATE</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">
   NdisAllocateMemoryWithTagPriority</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfrestartcomplete.md">NdisFRestartComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteeventlogentry.md">NdisWriteEventLogEntry</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569595">OID_GEN_LINK_STATE</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-miniport-restart-attributes">
   OID_GEN_MINIPORT_RESTART_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_RESTART callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>