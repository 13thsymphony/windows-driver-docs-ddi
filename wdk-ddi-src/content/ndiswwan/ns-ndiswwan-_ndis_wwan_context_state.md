---
UID: NS:ndiswwan._NDIS_WWAN_CONTEXT_STATE
title: "_NDIS_WWAN_CONTEXT_STATE"
author: windows-driver-content
description: The NDIS_WWAN_CONTEXT_STATE structure represents the Packet Data Protocol (PDP) context state of the MB device.
old-location: netvista\ndis_wwan_context_state.htm
old-project: netvista
ms.assetid: 7918ee03-c1cb-4a38-8773-4a01832357d2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndiswwan/NDIS_WWAN_CONTEXT_STATE, netvista.ndis_wwan_context_state, PNDIS_WWAN_CONTEXT_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_CONTEXT_STATE, *PNDIS_WWAN_CONTEXT_STATE, ndiswwan/PNDIS_WWAN_CONTEXT_STATE, NDIS_WWAN_CONTEXT_STATE, PNDIS_WWAN_CONTEXT_STATE, NDIS_WWAN_CONTEXT_STATE structure [Network Drivers Starting with Windows Vista], WwanRef_87098fc7-4dbd-4331-81a4-53d425cc0bb0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndiswwan.h
apiname:
-	NDIS_WWAN_CONTEXT_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_CONTEXT_STATE, *PNDIS_WWAN_CONTEXT_STATE
---

# _NDIS_WWAN_CONTEXT_STATE structure
The NDIS_WWAN_CONTEXT_STATE structure represents the Packet Data Protocol (PDP) context state of the
  MB device.

## Syntax
````
typedef struct _NDIS_WWAN_CONTEXT_STATE {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_CONTEXT_STATE ContextState;
} NDIS_WWAN_CONTEXT_STATE, *PNDIS_WWAN_CONTEXT_STATE;
````

## Members


`ContextState`

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_context_state.md">WWAN_CONTEXT_STATE</a> object that
     represents the Packet Data Protocol (PDP) context state of the device.

`Header`

The header with type, revision, and size information about the NDIS_WWAN_CONTEXT_STATE structure.
     The MB Service sets the header with the values that are shown in the following table when it sends the
     data structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     
<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
Windows 8 miniport drivers should set this to NDIS_WWAN_CONTEXT_STATE_REVISION_2. Windows 7 miniport drivers should set this to NDIS_WWAN_CONTEXT_STATE_REVISION_1.

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_CONTEXT_STATE)

</td>
</tr>
</table> 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`uStatus`

The status of context activation or deactivation operation. The following table shows the possible
     values for this member.
     
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_SUCCESS

</td>
<td>
Context activation or deactivation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
The operation failed. Miniport drivers can return this value if the context has already been
        activated.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
The operation failed because the device requires a PIN.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
The operation failed because a bad SIM card was detected.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
The operation failed because the SIM card was not inserted fully into the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        after the ready-state of the device changes to 
        <b>WwanReadyStateInitialized</b>.

</td>
</tr>
</table> 

Miniport drivers can return the following error codes (in addition to those previously described)
     only in the event of a failed set PDP activation operation.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_RADIO_POWER_OFF

</td>
<td>
The operation failed because the radio is currently turned off. This error code should be returned
        only in response to a OID_WWAN_CONNECT 
        <i>set</i> request. If the radio state is off then the miniport driver should respond to
        OID_WWAN_CONNECT 
        <i>query</i> requests with WWAN_STATUS_SUCCESS and specify the current context state as 
        <b>WwanActivationStateDeactivated</b>.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SERVICE_NOT_ACTIVATED

</td>
<td>
The operation failed because either the subscription has expired, or the device does not allow PDP
        activation.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PROVIDER_NOT_VISIBLE

</td>
<td>
The operation failed because the service provider is not currently visible.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_MAX_ACTIVATED_CONTEXTS

</td>
<td>
The operation failed because the maximum number of activated contexts has been reached.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_INVALID_ACCESS_STRING

</td>
<td>
The operation failed because the access string is invalid.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_INVALID_USER_NAME_PWD

</td>
<td>
The operation failed because the user name and/or password supplied are invalid. Network specific
        error code may be available in 
        <b>uNwError</b> .

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PACKET_SVC_DETACHED

</td>
<td>
The operation failed because packet service is detached.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_REGISTERED

</td>
<td>
The operation failed because the device is not in the registered state to perform PDP
        activation.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_VOICE_CALL_IN_PROGRESS

</td>
<td>
The operation failed and cannot proceed with PDP activation because a voice call is currently in
        progress. This value applies only to devices with voice class is set to 
        <b>WwanVoiceClassSeparateVoiceData</b>.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_CONTEXT_NOT_ACTIVATED

</td>
<td>
The operation failed because the context identified by 
        <b>ConnectionId</b> is not the currently activated context.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\wwan\ns-wwan-_wwan_context_state.md">WWAN_CONTEXT_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_CONTEXT_STATE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>