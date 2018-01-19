---
UID : NF:fwpsk.FwpsPendClassify0
title : FwpsPendClassify0 function
author : windows-driver-content
description : A callout's classifyFn function calls FwpsPendClassify0 to pend the current classify request.
old-location : netvista\fwpspendclassify0.htm
old-project : netvista
ms.assetid : 8abf967f-776e-4438-b20a-d7c278793633
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : FwpsPendClassify0
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
req.alt-api : FwpsPendClassify0
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


# FwpsPendClassify0 function
A callout's 
  <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function calls 
  <b>FwpsPendClassify0</b> to pend the current classify request. After the request is pended, the callout driver must complete
  the processing of the classify request asynchronously by calling 
  <a href="..\fwpsk\nf-fwpsk-fwpscompleteclassify0.md">FwpsCompleteClassify0</a>.

## Syntax

````
NTSTATUS NTAPI FwpsPendClassify0(
  _In_    UINT64             classifyHandle,
  _In_    UINT64             filterId,
  _In_    UINT32             flags,
  _Inout_ FWPS_CLASSIFY_OUT0 *classifyOut
);
````

## Parameters

`classifyHandle`

The classification handle that identifies the callout driver's processing at the current layer.
     This handle is obtained by calling 
     <a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">
     FwpsAcquireClassifyHandle0</a>.

`filterId`

The value of the 
     <b>FilterId</b> member of the 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function's 
     <i>filter</i> parameter. For more information about the 
     <b>FilterId</b> member, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>.

`flags`

Reserved for future use. Set to zero.

`classifyOut`

Set to the 
     <i>classifyOut</i> parameter of the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function. The 
     <i>classifyOut</i> parameter of 
     <i>classifyFn</i> is listed as an output parameter in the header, but it contains enough information on
     input to be useful to the engine when passed to 
     <b>FwpsPendClassify</b>.


## Return Value

The 
     <b>FwpsPendClassify0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The classify request was successfully pended.
<dl>
<dt><b>STATUS_FWP_CANNOT_PEND</b></dt>
</dl>The engine does not allow asynchronous classification at the layer from which the call was
       made.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

## Remarks

<b>FwpsPendClassify0</b> puts the classification of the indicated event in a pended state. A callout
    driver typically pends classification so that more processing can be done outside the scope of the 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function. The callout driver can
    then pass the classification handle and any other pertinent data about the indication to a function with
    less impact on performance than the driver callout functions. When processing is complete, the callout
    must call 
    <a href="..\fwpsk\nf-fwpsk-fwpscompleteclassify0.md">FwpsCompleteClassify0</a> to remove
    the pended state. At the time of the call to FwpsCompleteClassify, the callout driver must return a
    filled-out 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure just as it
    would in an inline classification.

FwpsPendClassify0 increments the reference count for the classification handle passed in the 
    <i>classifyHandle</i> parameter. After the callout driver calls this function, it can call 
    <a href="..\fwpsk\nf-fwpsk-fwpsreleaseclassifyhandle0.md">
    FwpsReleaseClassifyHandle0</a> to release the local instance. When <a href="..\fwpsk\nf-fwpsk-fwpscompleteclassify0.md">FwpsCompleteClassify0</a> is called, the
    reference to the handle will be decremented automatically.

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
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">FwpsAcquireClassifyHandle0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscompleteclassify0.md">FwpsCompleteClassify0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsreleaseclassifyhandle0.md">FwpsReleaseClassifyHandle0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsPendClassify0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>