---
UID: NS:fwpsk.FWPS_CALLOUT2_
title: FWPS_CALLOUT2_
author: windows-driver-content
description: The FWPS_CALLOUT2 structure defines the data that is required for a callout driver to register a callout with the filter engine.Note  FWPS_CALLOUT2 is the specific version of FWPS_CALLOUT used in Windows 8 and later.
old-location: netvista\fwps_callout2.htm
old-project: netvista
ms.assetid: 88d5a5ad-b71a-49b3-a1cf-b0dff1a85745
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: FWP_CALLOUT_FLAG_ALLOW_OFFLOAD, FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW, FWP_CALLOUT_FLAG_RESERVED1, FWP_CALLOUT_FLAG_ALLOW_RSC, FWP_CALLOUT_FLAG_ALLOW_RECLASSIFY, netvista.fwps_callout2, FWPS_CALLOUT2_, FWP_CALLOUT_FLAG_ENABLE_COMMIT_ADD_NOTIFY, fwpsk/FWPS_CALLOUT2, FWPS_CALLOUT2, FWPS_CALLOUT2 structure [Network Drivers Starting with Windows Vista], FWP_CALLOUT_FLAG_ALLOW_MID_STREAM_INSPECTION, FWP_CALLOUT_FLAG_ALLOW_L2_BATCH_CLASSIFY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fwpsk.h
apiname:
-	FWPS_CALLOUT2
product: Windows
targetos: Windows
req.typenames: FWPS_CALLOUT2
---

# FWPS_CALLOUT2_ structure
The <b>FWPS_CALLOUT2</b> structure defines the data that is required for a callout driver to register a
  callout with the filter engine.<div class="alert"><b>Note</b>  <b>FWPS_CALLOUT2</b> is the specific version of <b>FWPS_CALLOUT</b> used in Windows 8 and later. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 7, <a href="..\fwpsk\ns-fwpsk-fwps_callout1_.md">FWPS_CALLOUT1</a> is available. For Windows Vista, <a href="..\fwpsk\ns-fwpsk-fwps_callout0_.md">FWPS_CALLOUT0</a> is available.</div>
<div> </div>

## Syntax
````
typedef struct FWPS_CALLOUT2_ {
  GUID                                calloutKey;
  UINT32                              flags;
  FWPS_CALLOUT_CLASSIFY_FN2           classifyFn;
  FWPS_CALLOUT_NOTIFY_FN2             notifyFn;
  FWPS_CALLOUT_FLOW_DELETE_NOTIFY_FN0 flowDeleteFn;
} FWPS_CALLOUT2;
````

## Members


`calloutKey`

A callout driver-defined <b>GUID</b> that uniquely identifies the callout.

`classifyFn`

A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn2.md">classifyFn2</a> callout function. The filter
     engine calls this function whenever there is network data to be processed by the callout.

`flags`

Flags that specify callout-specific parameters. Possible flags are:
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW"></a><a id="fwp_callout_flag_conditional_on_flow"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
A callout driver can specify this flag when registering a callout that will be added at a layer
       that supports data flows. If this flag is specified, the filter engine calls the callout driver's 
       <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn2.md">classifyFn2</a> callout function only if there
       is a context associated with the data flow. A callout driver associates a context with a data flow by
       calling the 
       <a href="..\fwpsk\nf-fwpsk-fwpsflowassociatecontext0.md">FwpsFlowAssociateContext0</a> function.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_ALLOW_OFFLOAD"></a><a id="fwp_callout_flag_allow_offload"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_ALLOW_OFFLOAD</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
A callout driver specifies this flag to indicate that the callout driver's 
       <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn2.md">classifyFn2</a> callout function is unaffected
       by offloading network data processing to offload-capable network interface cards (NICs). If this flag
       is not specified, then offloading of network data processing is disabled for all traffic that is
       processed by any filters that specify the callout for the filter's action.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_ENABLE_COMMIT_ADD_NOTIFY"></a><a id="fwp_callout_flag_enable_commit_add_notify"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_ENABLE_COMMIT_ADD_NOTIFY</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
A callout driver specifies this flag to indicate that it can receive notifications about objects and filters that are added inside a transaction. The filter engine sends the notification after the transaction is committed.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_ALLOW_MID_STREAM_INSPECTION"></a><a id="fwp_callout_flag_allow_mid_stream_inspection"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_ALLOW_MID_STREAM_INSPECTION</b></dt>
<dt>0x00000008</dt>
</dl>
</td>
<td width="60%">
A callout driver specifies this flag to indicate that it can perform  dynamic stream inspection of data flows at stream level. See <a href="https://msdn.microsoft.com/77e152bf-cb6b-4845-9a5e-9c37281f23f1">Stream Inspection</a>.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_ALLOW_RECLASSIFY"></a><a id="fwp_callout_flag_allow_reclassify"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_ALLOW_RECLASSIFY</b></dt>
<dt>0x00000010</dt>
</dl>
</td>
<td width="60%">
A callout driver specifies this flag to register itself to be called when an existing socket operation is reclassified.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_RESERVED1"></a><a id="fwp_callout_flag_reserved1"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_RESERVED1</b></dt>
<dt>0x00000020</dt>
</dl>
</td>
<td width="60%">
Reserved for system use. Callout drivers should ignore this flag.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_ALLOW_RSC"></a><a id="fwp_callout_flag_allow_rsc"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_ALLOW_RSC</b></dt>
<dt>0x00000040</dt>
</dl>
</td>
<td width="60%">
A callout driver specifies this flag to indicate that the callout supports receive segment coalescing (RSC) with large packets of up to 64K. If this flag is not specified, and a callout is registered, then RSC is disabled for all traffic that is processed by any filters that specify the callout for the filter's action.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_ALLOW_L2_BATCH_CLASSIFY"></a><a id="fwp_callout_flag_allow_l2_batch_classify"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_ALLOW_L2_BATCH_CLASSIFY</b></dt>
<dt>0x00000080</dt>
</dl>
</td>
<td width="60%">
A callout driver specifies this flag when registering a callout that will be added at layer 2, to indicate that its <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn2.md">classifyFn2</a> callout function can classify multiple chained <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures. For more info, see <a href="https://msdn.microsoft.com/679E6DE2-4EFB-44F6-936D-2BF611BC9726">Using Layer 2 Filtering</a>.

<div class="alert"><b>Caution</b>  <p class="note">If a callout driver sets this flag, it cannot use the following functions to modify NET_BUFFER_LISTs.

<ul>
<li>
<a href="..\fwpsk\nf-fwpsk-fwpsreferencenetbufferlist0.md">FwpsReferenceNetBufferList0</a>
</li>
<li>
<a href="..\fwpsk\nf-fwpsk-fwpsdereferencenetbufferlist0.md">FwpsDereferenceNetBufferList0</a>
</li>
<li>
<a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">FwpsAllocateCloneNetBufferList0</a>
</li>
<li>
<a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">FwpsFreeCloneNetBufferList0</a>
</li>
</ul>
<p class="note">With this flag set, <b>FwpsAllocateCloneNetBufferList0</b> will always return an <b>INVALID_PARAMETER</b> error. This may unexpectedly cause a 3rd party callout driver to fail to manage the reference count of NET_BUFFER_LISTs, causing send and receive operations to stop.

</div>
<div> </div>
</td>
</tr>
</table>

`flowDeleteFn`

A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a> callout function. The filter
     engine calls this function whenever a data flow that is being processed by the callout is terminated.
     

If a callout driver does not associate a context with the data flows that the callout processes, then
     this member should be set to NULL.

`notifyFn`

A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn2.md">notifyFn2</a> function. The filter engine calls
     this function to notify the callout driver about events that are associated with the callout.

## Remarks
A callout driver passes a pointer to an initialized <b>FWPS_CALLOUT2</b> structure to the 
    <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister2.md">FwpsCalloutRegister2</a> function when it
    registers a callout with the filter engine.

A callout can set the <b>FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW</b> flag only for connections on which
    the driver is interested in performing stream inspections. This callout will be ignored on all other
    connections. Performance will be improved and the driver will not have to maintain unnecessary state
    data.

This structure is essentially identical to the previous version, 
    <a href="..\fwpsk\ns-fwpsk-fwps_callout1_.md">FWPS_CALLOUT1</a>. The only differences are that
    the members of this version store the updated versions of the callout function pointers, and additional flags are available for callout drivers to set.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | fwpsk.h (include Fwpsk.h) |

## See Also

<a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a>



<a href="https://msdn.microsoft.com/679E6DE2-4EFB-44F6-936D-2BF611BC9726">Using Layer 2 Filtering</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn2.md">notifyFn2</a>



<a href="..\fwpsk\ns-fwpsk-fwps_callout0_.md">FWPS_CALLOUT0</a>



<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister2.md">FwpsCalloutRegister2</a>



<a href="..\fwpsk\ns-fwpsk-fwps_callout1_.md">FWPS_CALLOUT1</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn2.md">classifyFn2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_CALLOUT2 structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>