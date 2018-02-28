---
UID: NC:ucmmanager.EVT_UCM_CONNECTOR_SET_POWER_ROLE
title: EVT_UCM_CONNECTOR_SET_POWER_ROLE
author: windows-driver-content
description: The client driver's implementation of the EVT_UCM_CONNECTOR_SET_POWER_ROLE event callback function that sets the power role of the connector to the specified role when attached to a partner connector.
old-location: buses\evt_ucm_connector_set_power_role.htm
old-project: usbref
ms.assetid: 56D5A78D-546E-439E-A69E-A87B0A3B288F
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UCM_CONNECTOR_SET_POWER_ROLE, EvtSetDataRole, EvtSetDataRole callback function [Buses], PFN_UCM_CONNECTOR_SET_POWER_ROLE, PFN_UCM_CONNECTOR_SET_POWER_ROLE callback function pointer [Buses], buses.evt_ucm_connector_set_power_role, ucmmanager/EvtSetDataRole
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ucmmanager.h
api_name:
-	PFN_UCM_CONNECTOR_SET_POWER_ROLE
product: Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---


# EVT_UCM_CONNECTOR_SET_POWER_ROLE callback function
The client driver's implementation of the <i>EVT_UCM_CONNECTOR_SET_POWER_ROLE</i> event callback function that sets the power  role of the connector to the specified role when attached to a partner connector.

## Syntax

```
EVT_UCM_CONNECTOR_SET_POWER_ROLE EvtUcmConnectorSetPowerRole;

NTSTATUS EvtUcmConnectorSetPowerRole(
  UCMCONNECTOR Connector,
  UCM_POWER_ROLE PowerRole
)
{...}
```

## Parameters

`Connector`

Handle to the connector that the client driver received in a previous call to  the <a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a> method.

`PowerRole`

A <a href="..\ucmtypes\ne-ucmtypes-_ucm_power_role.md">UCM_POWER_ROLE</a>-typed flag that specifies the role to set.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## Remarks

To register an <i>EVT_UCM_CONNECTOR_SET_POWER_ROLE</i> callback function, the client must call <a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>.

The USB connector manager framework extension (UcmCx) can request either <b>UcmPowerRoleSink</b> or  <b>UcmPowerRoleSource</b>. If the port is already in the requested role, the client driver can complete the request without any changes. Otherwise, it starts a power-role swap operation (PR_Swap). The driver calls <a href="..\ucmmanager\nf-ucmmanager-ucmconnectorpowerdirectionchanged.md">UcmConnectorPowerDirectionChanged</a> to notify UcmCx about the success or failure of that operation. 
The driver can call that method within the callback function.

The role persists for the current connection.  

If a role-swap operation is pending, UcmCx does not request another role swap. Those operations are serialized across power and data role swaps.

After the swap operation completes, if the partner port sends a PR_Swap request, the client driver must reject the request. 


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UCM_CONNECTOR_SET_POWER_ROLE     EvtSetPowerRole;  

NTSTATUS  
EvtSetPowerRole(  
    UCMCONNECTOR Connector,  
    UCM_POWER_ROLE PowerRole  
    )  
{  
    PCONNECTOR_CONTEXT connCtx;  
  
    TRACE_INFO("EvtSetPowerRole(%!UCM_POWER_ROLE!) Entry", PowerRole);  
  
    connCtx = GetConnectorContext(Connector);  

    //PR_Swap operation.  
  
  
    TRACE_FUNC_EXIT();  
    return STATUS_SUCCESS;  
}  
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmmanager.h (include Ucmcx.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCM_CONNECTOR_SET_POWER_ROLE callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>