---
UID : NF:fwpsk.FwpsApplyModifiedLayerData0
title : FwpsApplyModifiedLayerData0 function
author : windows-driver-content
description : The FwpsApplyModifiedLayerData0 function applies changes to layer-specific data made after a call to FwpsAcquireWritableLayerDataPointer0.Note  FwpsApplyModifiedLayerData0 is a specific version of FwpsApplyModifiedLayerData.
old-location : netvista\fwpsapplymodifiedlayerdata0.htm
old-project : netvista
ms.assetid : d32c19b6-462e-48e3-b22b-02542dca9cc4
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : FwpsApplyModifiedLayerData0 function [Network Drivers Starting with Windows Vista], FWPS_CLASSIFY_FLAG_REAUTHORIZE_IF_MODIFIED_BY_OTHERS, FwpsApplyModifiedLayerData0, netvista.fwpsapplymodifiedlayerdata0, fwpsk/FwpsApplyModifiedLayerData0, wfp_ref_2_funct_3_fwps_A-B_a7adbeec-b234-451e-9da0-d5e5b7cefc90.xml
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Fwpkclnt.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : FWPS_VSWITCH_EVENT_TYPE
---


# FwpsApplyModifiedLayerData0 function
The 
  <b>FwpsApplyModifiedLayerData0</b> function applies changes to layer-specific data made after a call to 
  <a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">FwpsAcquireWritableLayerDataPointer0</a>.
<div class="alert"><b>Note</b>  <b>FwpsApplyModifiedLayerData0</b> is a specific version of <b>FwpsApplyModifiedLayerData</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

````
void NTAPI FwpsApplyModifiedLayerData0(
  _In_ UINT64 classifyHandle,
  _In_ PVOID  modifiedLayerData,
  _In_ UINT32 flags
);
````

## Parameters

`classifyHandle`

The classification handle that identifies the callout driver's processing at the current layer.
     This handle is obtained by calling 
     <a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">
     FwpsAcquireClassifyHandle0</a>.

`modifiedLayerData`

The data buffer obtained by calling 
     <a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">FwpsAcquireWritableLayerDataPointer0</a> with members modified by the callout driver. Supported data
     types are defined as structures.

`flags`

The options to use with this function call. This flag can have the following
      value.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FWPS_CLASSIFY_FLAG_REAUTHORIZE_IF_MODIFIED_BY_OTHERS"></a><a id="fwps_classify_flag_reauthorize_if_modified_by_others"></a><dl>
<dt><b>FWPS_CLASSIFY_FLAG_REAUTHORIZE_IF_MODIFIED_BY_OTHERS</b></dt>
</dl>
</td>
<td width="60%">
When set, this flag specifies that data at the layer of the pended classify action should be reauthorized if another callout driver modifies the data before the classification is completed. Use this flag only with pended classify and not inline classify, as its use with inline classify can lead to indeterminate results. If you do call this API for inline classify, set flags to zero.

</td>
</tr>
</table>


## Return Value

None.

## Remarks

<b>FwpsApplyModifiedLayerData0</b> should be called once for every call made to 
    <a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">FwpsAcquireWritableLayerDataPointer0</a>, even if the callout driver didn't modify any data.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 7. Available starting with Windows 7. |
| **Target Platform** | Universal |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** | Fwpkclnt.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\fwpsk\nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md">
   FwpsAcquireWritableLayerDataPointer0</a>

<a href="..\fwpsk\ns-fwpsk-_fwps_bind_request0.md">FWPS_BIND_REQUEST0</a>

<a href="..\fwpsk\ns-fwpsk-_fwps_connect_request0.md">FWPS_CONNECT_REQUEST0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">FwpsAcquireClassifyHandle0</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>

<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>

<a href="..\fwpsk\nf-fwpsk-fwpsreleaseclassifyhandle0.md">FwpsReleaseClassifyHandle0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsApplyModifiedLayerData0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>