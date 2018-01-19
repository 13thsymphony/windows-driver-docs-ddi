---
UID : NF:fwpsk.FwpsAcquireWritableLayerDataPointer0
title : FwpsAcquireWritableLayerDataPointer0 function
author : windows-driver-content
description : The FwpsAcquireWritableLayerDataPointer0 function returns layer-specific data that can be inspected and changed.Note  FwpsAcquireWritableLayerDataPointer0 is a specific version of FwpsAcquireWritableLayerDataPointer.
old-location : netvista\fwpsacquirewritablelayerdatapointer0.htm
old-project : netvista
ms.assetid : 79816d01-bf27-49d0-b6f1-083b7e87cc4e
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : FwpsAcquireWritableLayerDataPointer0
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 7.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FwpsAcquireWritableLayerDataPointer0
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


# FwpsAcquireWritableLayerDataPointer0 function
The 
  <b>FwpsAcquireWritableLayerDataPointer0</b> function returns layer-specific data that can be inspected and
  changed.

## Syntax

````
NTSTATUS NTAPI FwpsAcquireWritableLayerDataPointer0(
  _In_    UINT64             classifyHandle,
  _In_    UINT64             filterId,
  _In_    UINT32             flags,
  _Out_   PVOID              *writableLayerData,
  _Inout_ FWPS_CLASSIFY_OUT0 *classifyOut
);
````

## Parameters

`classifyHandle`

A handle for the classify request.
     This handle is obtained by calling 
     <a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">
     FwpsAcquireClassifyHandle0</a>.

`filterId`

The value of the 
     <b>FilterId</b> member of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> function's 
     <i>filter</i> parameter. For more information about the 
     <b>FilterId</b> member, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>.

`flags`

Reserved for future use. Set to zero.

`writableLayerData`

A data buffer that contains the modifiable data for the layer. The supported data types, which are listed in the following Remarks section, are defined as
     structures. On return, the data can be accessed by casting the void pointer to the appropriate structure
     type.

`classifyOut`

Set to the 
     <i>classifyOut</i> parameter of the callout driver's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> function. The 
     <i>classifyOut</i> parameter of 
     classifyFn is listed as an output parameter in the header, but it contains enough information on
     input to be useful to the engine when passed to 
     <b>FwpsAcquireWritableLayerDataPointer0</b>.


## Return Value

The 
     <b>FwpsAcquireWritableLayerDataPointer0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callback function was successfully registered.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

## Remarks

<b>FwpsAcquireWritableLayerDataPointer0</b> sets the following members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure:<ul>
<li><i>classifyOut</i>-&gt;<b>actionType</b> = <b>FWP_ACTION_BLOCK</b></li>
<li><i>classifyOut</i>-&gt;<b>rights</b> = ~<b>FWPS_RIGHT_ACTION_WRITE</b></li>
</ul>


For every call to this function, you must make a matching call to 
    <a href="..\fwpsk\nf-fwpsk-fwpsapplymodifiedlayerdata0.md">FwpsApplyModifiedLayerData0</a> to
    finalize the changes that were made, even if your callout driver didn't modify any data. If you do not make the call to <b>FwpsApplyModifiedLayerData0</b>, this could result in the classify not completing correctly.

The following structures are defined to contain modifiable layer data. The pointer set on output as
    the 
    <i>writableLayerData</i> parameter can be cast to one of these types:


<a href="..\fwpsk\ns-fwpsk-_fwps_bind_request0.md">FWPS_BIND_REQUEST0</a>



<a href="..\fwpsk\ns-fwpsk-_fwps_connect_request0.md">FWPS_CONNECT_REQUEST0</a>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>
</dt>
<dt>
<a href="..\fwpsk\ns-fwpsk-_fwps_bind_request0.md">FWPS_BIND_REQUEST0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a>
</dt>
<dt>
<a href="..\fwpsk\ns-fwpsk-_fwps_connect_request0.md">FWPS_CONNECT_REQUEST0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">FwpsAcquireClassifyHandle0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsapplymodifiedlayerdata0.md">FwpsApplyModifiedLayerData0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsreleaseclassifyhandle0.md">FwpsReleaseClassifyHandle0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsAcquireWritableLayerDataPointer0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>