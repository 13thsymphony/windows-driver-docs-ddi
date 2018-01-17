---
UID: NC:ndis.PROTOCOL_CM_MODIFY_QOS_CALL
title: PROTOCOL_CM_MODIFY_QOS_CALL function
author: windows-driver-content
description: The ProtocolCmModifyCallQoS function is required.
old-location: netvista\protocolcmmodifycallqos.htm
old-project: netvista
ms.assetid: 24523677-9f5a-4109-8484-95883a4d1bbf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PROTOCOL_CM_MODIFY_QOS_CALL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmModifyCallQoS (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmModifyCallQoS (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolCmModifyCallQoS
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
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CM_MODIFY_QOS_CALL function



## -description
The 
  <i>ProtocolCmModifyCallQoS</i> function is required. 
  <i>ProtocolCmModifyCallQoS</i> is called by NDIS when a connection-oriented client requests that the call
  parameters be changed for an existing virtual connection (VC). If the underlying network medium does not
  support QoS, 
  <i>ProtocolCmModifyQoS</i> should simply return NDIS_STATUS_NOT_SUPPORTED.



## -syntax

````
PROTOCOL_CM_MODIFY_QOS_CALL ProtocolCmModifyCallQoS;

NDIS_STATUS ProtocolCmModifyCallQoS(
  _In_ NDIS_HANDLE         CallMgrVcContext,
  _In_ PCO_CALL_PARAMETERS CallParameters
)
{ ... }
````


## -parameters

### -param CallMgrVcContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-VC state. The call manager supplied this handle to NDIS for its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


### -param CallParameters [in]

Pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> structure that contains
     the new call parameters, as specified by a connection-oriented client, for the VC.


## -returns
<i>ProtocolCmModifyQoS</i> returns the status of its operation(s) as one of the following values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>Indicates that the call manager successfully changed the parameters of the call with the network
       to the call parameters specified at 
       <i>CallParameters</i> .
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>Indicates that the call manager will complete the request to modify the call parameters
       asynchronously. When the call manager has completed all operations necessary to modify the call
       parameters, it must call 
       <a href="..\ndis\nf-ndis-ndiscmmodifycallqoscomplete.md">
       NdisCmModifyCallQoSComplete</a>.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>Indicates that the call manager could not change the call parameters of the VC because
       dynamically allocated resources were not available.
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>Indicates that the call manager was unable to change the call parameters of the VC because the
       call parameters provided at 
       <i>CallParameters</i> were illegal or invalid.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>Indicates that the call parameters could not be set to the call parameters provided because of a
       failure in the network or in another connection-oriented network component.

 


## -remarks
<i>ProtocolCmModifyQoS</i> communicates with network control devices or other media-specific agents, as
    necessitated by its media, to modify the media-specific call parameters for an established virtual
    connection. If the call manager is required to communicate with network control agents (in other words, a
    networking switch) it should use a virtual connection to the network control agents that it established
    in its 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function.
    Stand-alone call managers communicated to the network agents by calling 
    <a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>.
    Miniport drivers with integrated call-management support never call 
    <b>NdisCoSendNetBufferLists</b>. Instead, such a driver simply transfers the data over the network to the
    target network agent.

After communicating with the network and if the changes were successful, the call manager must then
    call 
    <a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a> with the new call
    parameters. This notifies NDIS and/or the connection-oriented miniport driver that the call parameters
    have changed and provides the miniport driver with an opportunity to validate those parameters.

If either the network cannot accept the new call parameters or the underlying miniport driver cannot
    accept the parameters, the call manager must restore the virtual connection to the state that existed
    before any modifications were attempted, and return NDIS_STATUS_FAILURE.

To define a <i>ProtocolCmModifyCallQoS</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmModifyCallQoS</i> function that is named "MyCmModifyCallQoS", use the <b>PROTOCOL_CM_MODIFY_QOS_CALL</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CM_MODIFY_QOS_CALL</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_MODIFY_QOS_CALL</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmmodifycallqoscomplete.md">NdisCmModifyCallQoSComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_MODIFY_QOS_CALL callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

