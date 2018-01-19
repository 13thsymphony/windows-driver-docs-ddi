---
UID : NC:ndis.FILTER_OID_REQUEST
title : FILTER_OID_REQUEST
author : windows-driver-content
description : NDIS calls a filter driver's FilterOidRequest function to process an OID request that is associated with the specified filter module.Note  You must declare the function by using the FILTER_OID_REQUEST type.
old-location : netvista\filteroidrequest.htm
old-project : netvista
ms.assetid : 238bfa21-a971-4fe4-a774-6ba834efc3c5
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
req.alt-api : FilterOidRequest
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
req.irql : <= DISPATCH_LEVEL
req.typenames : VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# FILTER_OID_REQUEST function
NDIS calls a filter driver's 
  <i>FilterOidRequest</i> function to process an OID request that is associated with the specified filter
  module.

## Syntax

```
FILTER_OID_REQUEST FilterOidRequest;

NDIS_STATUS FilterOidRequest(
  NDIS_HANDLE FilterModuleContext,
  PNDIS_OID_REQUEST OidRequest
)
{...}
```

## Parameters

`FilterModuleContext`

A handle to the context area for the filter module that is the target of this request. The filter
     driver created and initialized this context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

`OidRequest`

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that specifies
     the operation requested including the OID_<i>XXX</i> code. The structure can specify either an OID  query request or an OID set request. For more information
     about OIDs, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566707">NDIS OIDs</a>.


## Return Value

<i>FilterOidRequest</i> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><i>FilterOidRequest</i> successfully completed the filter driver's query or set operation for this
       filter module.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>Indicates that the filter driver will complete the request asynchronously. After the driver
       completes the request, it must call the 
       <a href="..\ndis\nf-ndis-ndisfoidrequestcomplete.md">
       NdisFOidRequestComplete</a> function to inform NDIS that the request is complete.
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>Indicates that the request, specified at 
       <i>OidRequest</i>, is invalid or not recognized.
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl><i>FilterOidRequest</i> does not support the OID, the OID is optional.
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>Indicates that the buffer, supplied at 
       <i>OidRequest</i>, is too small to hold the requested data.
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH</b></dt>
</dl>For a query operation, the 
       <b>InformationBufferLength</b> member of the 
       <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure does not
       match the length required by the given OID. 
       <i>FilterOidRequest</i> returned the required buffer size, in bytes, in the 
       <b>BytesNeeded</b> member of the NDIS_OID_REQUEST structure.
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>For a set operation, the data supplied in the 
       <b>InformationBuffer</b> member of the NDIS_OID_REQUEST structure was invalid for the given OID.
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl><i>FilterOidRequest</i> attempted to gather the requested information but was unsuccessful.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><i>FilterOidRequest</i> failed due to insufficient resources.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl><i>FilterOidRequest</i> returns NDIS_STATUS_FAILURE if none of the preceding values applies. The filter
       driver should call the 
       <a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a> function
       with parameters that specify the reason for the failure.

## Remarks

<i>FilterOidRequest</i> is an optional function. If a filter driver does not use OID requests, it can set
    the entry point for this function to <b>NULL</b> when it calls the 
    <b>NdisFRegisterFilterDriver</b> function. If a filter driver defines a 
    <i>FilterOidRequestComplete</i> function, it must provide the 
    <i>FilterOidRequest</i> function.

NDIS calls the filter driver's 
    <i>FilterOidRequest</i> function to process OID requests that are originated by overlying drivers. Filter
    drivers can forward such requests to underlying drivers by calling the 
    <a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a> function.

Before the driver calls 
    <b>NdisFOidRequest</b>, the driver must allocate an 
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure and transfer the
    request information to the new structure by calling 
    <a href="..\ndis\nf-ndis-ndisallocatecloneoidrequest.md">NdisAllocateCloneOidRequest</a>.
    As an option, a filter driver can complete a request immediately without forwarding the request.

To complete a request synchronously, the filter driver returns NDIS_STATUS_SUCCESS or a failure
    status. If the driver returns NDIS_STATUS_PENDING, it must call the 
    <a href="..\ndis\nf-ndis-ndisfoidrequestcomplete.md">NdisFOidRequestComplete</a> function
    to inform NDIS that the request is complete.

For a query operation, 
    <i>FilterOidRequest</i> returns the requested information in the 
    <b>InformationBuffer</b> member and sets the variable in the 
    <b>BytesWritten</b> member of the NDIS_OID_REQUEST structure to the amount of information it returned. The
    underlying drivers do this if the filter driver passed the request on with 
    <b>NdisFOidRequest</b>.

For a set operation, <i>FilterOidRequest</i> can use the data in the 
    <b>InformationBuffer</b> member of the NDIS_OID_REQUEST structure to set the information required by the
    given OID. In this case, 
    <i>FilterOidRequest</i> sets the variable at 
    <b>BytesRead</b> to the amount of the supplied data that it used. The underlying drivers do this if the
    filter driver passed the request on with 
    <b>NdisFOidRequest</b>.

Like miniport drivers, filter drivers can receive only one request at a time. NDIS serializes requests
    that it sends to a filter driver. NDIS cannot call 
    <i>FilterOidRequest</i> before a filter driver completes the current request.

NDIS calls
    <i>FilterOidRequest</i> at IRQL &lt;= DISPATCH_LEVEL.

To define a <i>FilterOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterOidRequest</i> function that is named "MyOidRequest", use the <b>FILTER_OID_REQUEST</b> type as shown in this code example:

Then, implement your function as follows:

The <b>FILTER_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

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
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatecloneoidrequest.md">NdisAllocateCloneOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfoidrequestcomplete.md">NdisFOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_OID_REQUEST callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>