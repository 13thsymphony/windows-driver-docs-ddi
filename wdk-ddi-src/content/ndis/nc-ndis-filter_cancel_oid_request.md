---
UID: NC.ndis.FILTER_CANCEL_OID_REQUEST
title: FILTER_CANCEL_OID_REQUEST
author: windows-driver-content
description: NDIS calls a filter driver's FilterCancelOidRequest function to cancel an OID request.Note  You must declare the function by using the FILTER_CANCEL_OID_REQUEST type.
old-location: netvista\filtercanceloidrequest.htm
old-project: NetVista
ms.assetid: e7e3f67e-5353-4355-bf19-8a8041cafc84
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
req.alt-api: FilterCancelOidRequest
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
req.irql: <= DISPATCH_LEVEL
---

# FILTER_CANCEL_OID_REQUEST callback



## -description
NDIS calls a filter driver's 
  <i>FilterCancelOidRequest</i> function to cancel an OID request.



## -prototype

````
FILTER_CANCEL_OID_REQUEST FilterCancelOidRequest;

VOID FilterCancelOidRequest(
  _In_ NDIS_HANDLE FilterModuleContext,
  _In_ PVOID       RequestId
)
{ ... }
````


## -parameters

### -param FilterModuleContext [in]

A handle to the context area for the filter module that is the target of this request. The filter
     driver created and initialized this context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param RequestId [in]

A cancellation identifier for the request. This identifier specifies the 
     <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## -returns
None


## -remarks
<i>FilterCancelOidRequest</i> is an optional function. If a filter driver does not use OID requests, it
    can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="netvista.ndisfregisterfilterdriver">
    NdisFRegisterFilterDriver</a> function.

When NDIS calls 
    <i>FilterCancelOidRequest</i>, the filter driver should attempt to call 
    <a href="netvista.ndisfoidrequestcomplete">NdisFOidRequestComplete</a> function
    as soon as possible.

The request parameters are defined in the 
    <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structure at 
    <i>OidRequest</i> .

If a filter driver does not queue OID requests, the driver is not required to provide a 
    <i>FilterCancelOidRequest</i> function. If the filter driver does not specify a 
    <i>FilterCancelOidRequest</i> entry point, NDIS calls the cancel OID request function of the underlying
    driver.

NDIS calls the 
    <i>FilterCancelOidRequest</i> function either when the originator of the request cancels the request or
    when the time-out specified at the 
    <b>Timeout</b> member expires.

If the request processing is still not complete in a filter driver, the driver calls the 
    <b>NdisFOidRequestComplete</b> function with the status set to NDIS_STATUS_REQUEST_ABORTED.

If the filter driver forwarded the request to an underlying driver and the processing is still not
    complete, the filter driver calls the 
    <a href="netvista.ndisfcanceloidrequest">NdisFCancelOidRequest</a> function with
    the 
    <i>OidRequest</i> parameter set to the value that it sent to the underlying driver.

NDIS calls
    <i>FilterCancelOidRequest</i> at IRQL &lt;= DISPATCH_LEVEL.

To define a <i>FilterCancelOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterCancelOidRequest</i> function that is named "MyCancelOidRequest", use the <b>FILTER_CANCEL_OID_REQUEST</b> type as shown in this code example:

Then, implement your function as follows:

The <b>FILTER_CANCEL_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_CANCEL_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

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
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="netvista.ndisfcanceloidrequest">NdisFCancelOidRequest</a>
</dt>
<dt>
<a href="netvista.ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="netvista.ndisfoidrequestcomplete">NdisFOidRequestComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20FILTER_CANCEL_OID_REQUEST callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

