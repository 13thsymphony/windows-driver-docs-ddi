---
UID: NC:ndis.PROTOCOL_CM_MAKE_CALL
title: PROTOCOL_CM_MAKE_CALL
author: windows-driver-content
description: The ProtocolCmMakeCall function is a required function that sets up media specific parameters for a virtual connection (VC) and activates the virtual connection.Note  You must declare the function by using the PROTOCOL_CM_MAKE_CALL type.
old-location: netvista\protocolcmmakecall.htm
old-project: netvista
ms.assetid: ede0a18a-cd3b-4fbb-a16b-e7493940d633
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.protocolcmmakecall, ProtocolCmMakeCall callback function [Network Drivers Starting with Windows Vista], ProtocolCmMakeCall, PROTOCOL_CM_MAKE_CALL, PROTOCOL_CM_MAKE_CALL, ndis/ProtocolCmMakeCall, condis_call_manager_ref_4f72c0f7-470b-496c-adbb-ea465246fb48.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmMakeCall (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmMakeCall (NDIS   5.1)) in Windows XP.
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
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	ProtocolCmMakeCall
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---


# PROTOCOL_CM_MAKE_CALL function
The 
  <i>ProtocolCmMakeCall</i> function is a required function that sets up media specific parameters for a
  virtual connection (VC) and activates the virtual connection.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_MAKE_CALL</b> type.
   For more information, see the following Examples section.</div><div> </div>

## Syntax

```
PROTOCOL_CM_MAKE_CALL ProtocolCmMakeCall;

NDIS_STATUS ProtocolCmMakeCall(
  NDIS_HANDLE CallMgrVcContext,
  PCO_CALL_PARAMETERS CallParameters,
  NDIS_HANDLE NdisPartyHandle,
  PNDIS_HANDLE CallMgrPartyContext
)
{...}
```

## Parameters

`CallMgrVcContext`

Specifies the handle to a call manager-allocated context area in which the call managers maintains
     its per-VC state. The call manager supplied this handle to NDIS from its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.

`CallParameters`

Pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> structure that contains
     the parameters, specified by a connection-oriented client, for this outgoing call.

`NdisPartyHandle`

Specifies a handle, supplied by NDIS, that uniquely identifies the initial party on the multipoint
     virtual connection. This handle is opaque to the call manager and reserved for NDIS library use. This
     handle is <b>NULL</b> if the client is not setting up an outgoing multipoint call.

`CallMgrPartyContext`

On return, specifies a handle to a call manager-supplied context area in which the call manager
     maintains state about the initial party on the multipoint call. If 
     <i>NdisPartyHandle</i> is <b>NULL</b>, this handle must be set to <b>NULL</b>.


## Return Value

<i>ProtocolCmMakeCall</i> returns the status of its operation(s) as one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager successfully allocated the necessary resources to make the call
       and was able to activate the virtual connection with the miniport driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager will complete the request to make a call asynchronously. When
       the call manager has completed all operations for making a call, it must call 
       <a href="..\ndis\nf-ndis-ndiscmmakecallcomplete.md">NdisCmMakeCallComplete</a> to signal
       NDIS that this call has been completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager was unable to allocate and/or initialize its resources for
       activating the virtual connection as requested by the client.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager was unable to activate a virtual connection because the caller
       requested invalid or unavailable features in the call parameters specified at 
       <i>CallParameters</i> .

</td>
</tr>
</table>

## Remarks

If 
    <i>ProtocolCmMakeCall</i> is given an explicit 
    <i>NdisPartyHandle</i>, this VC was created by the client for a multipoint call. The call manager must
    allocate and initialize any necessary resources required to maintain state information and control a
    multipoint call. Such resources include, but are not limited to, memory buffers, data structures, events,
    and other similar resources. If the call manager cannot allocate or initialize the needed resources for
    its state area(s), it should return control to NDIS with NDIS_STATUS_RESOURCES.

<i>ProtocolCmMakeCall</i> communicates with network control devices or other media-specific actors, as
    necessary, to make a connection between the local node and a remote node based on the call parameters
    specified at 
    <i>CallParameters</i> . Such actions could include, but are not limited to, communication with switching
    hardware, communications with a network control station, or other actions as appropriate to the network
    medium.

If a call manager is required to communication with networking hardware (such as a networking switch)
    it should use a virtual connection to the network control device that it established in its 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function.
    Call managers communicate with their network hardware through the miniport driver by calling 
    <a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>.
    Miniport drivers with integrated call-management support will not call 
    <b>NdisCoSendNetBufferLists</b>, but rather will transmit the data themselves.

After a call manager has done all necessary communication with its networking hardware as required by
    its medium, call managers must call 
    <a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>.

If this call was a multipoint call, after the call manager has communicated with the networking
    hardware, verified call parameters, and allocated and initialized its per-party state data, the address
    of its state block should be set in the handle 
    <i>CallMgrPartyContext</i> before returning control to NDIS. The handle is set by dereferencing the handle
    and storing a pointer to the state block as the value of the handle. For example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>*CallMgrPartyContext = SomeBuffer ;</pre>
</td>
</tr>
</table></span></div>
If 
    <i>ProtocolCmMakeCall</i> has completed the required operations for its network and the VC has been
    successfully activated through 
    <b>NdisCmActivateVc</b>, 
    <i>ProtocolCmMakeCall</i> should return control as quickly as possible with a status of
    STATUS_SUCCESS.

After 
    <i>ProtocolCmMakeCall</i> returns control to NDIS, the call manager should expect to take no further
    actions on this call to set it up. 
    <i>ProtocolCmMakeCall</i> is responsible for establishing the connection so that the client can make data
    transfers over the network on this VC. However, the call manager can be called subsequently to modify the
    call's quality of service, to add or drop parties if this is a multipoint VC, and eventually to terminate
    this call.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmMakeCall</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmMakeCall</i> function that is named "MyCmMakeCall", use the <b>PROTOCOL_CM_MAKE_CALL</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CM_MAKE_CALL MyCmMakeCall;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NDIS_STATUS
 MyCmMakeCall(
    NDIS_HANDLE  CallMgrVcContext,
    PCO_CALL_PARAMETERS  CallParameters,
    NDIS_HANDLE  NdisPartyHandle,
    PNDIS_HANDLE  CallMgrPartyContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_MAKE_CALL</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_MAKE_CALL</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmMakeCall (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmMakeCall (NDIS   5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmMakeCall (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmMakeCall (NDIS   5.1)) in Windows XP. |
| **Target Platform** | Windows |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>



<a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>



<a href="..\ndis\nf-ndis-ndiscmmakecallcomplete.md">NdisCmMakeCallComplete</a>



<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_MAKE_CALL callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>