---
UID: NF:fwpsk.FwpsAcquireWritableLayerDataPointer0
title: FwpsAcquireWritableLayerDataPointer0 function
author: windows-driver-content
description: The FwpsAcquireWritableLayerDataPointer0 function returns layer-specific data that can be inspected and changed.Note  FwpsAcquireWritableLayerDataPointer0 is a specific version of FwpsAcquireWritableLayerDataPointer.
old-location: netvista\fwpsacquirewritablelayerdatapointer0.htm
old-project: netvista
ms.assetid: 79816d01-bf27-49d0-b6f1-083b7e87cc4e
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FwpsAcquireWritableLayerDataPointer0, FwpsAcquireWritableLayerDataPointer0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAcquireWritableLayerDataPointer0, netvista.fwpsacquirewritablelayerdatapointer0, wfp_ref_2_funct_3_fwps_A-B_adf2c5a7-ebcb-4c05-aa5a-3b794b60dc74.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsAcquireWritableLayerDataPointer0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---


# FwpsAcquireWritableLayerDataPointer0 function
The 
  <b>FwpsAcquireWritableLayerDataPointer0</b> function returns layer-specific data that can be inspected and
  changed.
<div class="alert"><b>Note</b>  <b>FwpsAcquireWritableLayerDataPointer0</b> is a specific version of <b>FwpsAcquireWritableLayerDataPointer</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

```
NTSTATUS FwpsAcquireWritableLayerDataPointer0(
  UINT64             classifyHandle,
  UINT64             filterId,
  UINT32             flags,
  PVOID              *writableLayerData,
  FWPS_CLASSIFY_OUT0 *classifyOut
);
```

## Parameters

`classifyHandle`

A handle for the classify request.
     This handle is obtained by calling 
     <a href="https://msdn.microsoft.com/7348d937-6541-47a7-ae70-7d851d41bc1a">
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

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callback function was successfully registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>

## Remarks

<b>FwpsAcquireWritableLayerDataPointer0</b> sets the following members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure:<ul>
<li><i>classifyOut</i>-&gt;<b>actionType</b> = <b>FWP_ACTION_BLOCK</b></li>
<li><i>classifyOut</i>-&gt;<b>rights</b> = ~<b>FWPS_RIGHT_ACTION_WRITE</b></li>
</ul>


For every call to this function, you must make a matching call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551137">FwpsApplyModifiedLayerData0</a> to
    finalize the changes that were made, even if your callout driver didn't modify any data. If you do not make the call to <b>FwpsApplyModifiedLayerData0</b>, this could result in the classify not completing correctly.

The following structures are defined to contain modifiable layer data. The pointer set on output as
    the 
    <i>writableLayerData</i> parameter can be cast to one of these types:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551221">FWPS_BIND_REQUEST0</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551231">FWPS_CONNECT_REQUEST0</a>


</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 7.  |
| **Target Platform** | Universal |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** | Fwpkclnt.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551221">FWPS_BIND_REQUEST0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551231">FWPS_CONNECT_REQUEST0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550085">FwpsAcquireClassifyHandle0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551137">FwpsApplyModifiedLayerData0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551208">FwpsReleaseClassifyHandle0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>