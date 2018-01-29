---
UID : NC:ndis.NDIS_SWITCH_DEREFERENCE_SWITCH_PORT
title : NDIS_SWITCH_DEREFERENCE_SWITCH_PORT
author : windows-driver-content
description : The DereferenceSwitchPort function decrements the Hyper-V extensible switch reference counter for an extensible switch port. The reference counter was incremented through a previous call to ReferenceSwitchPort.
old-location : netvista\DereferenceSwitchPort.htm
old-project : netvista
ms.assetid : 976D3A69-C539-4C8E-9664-F85717E5F712
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.DereferenceSwitchPort, DereferenceSwitchPort callback function [Network Drivers Starting with Windows Vista], DereferenceSwitchPort, NDIS_SWITCH_DEREFERENCE_SWITCH_PORT, NDIS_SWITCH_DEREFERENCE_SWITCH_PORT, ndis/DereferenceSwitchPort
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported in NDIS 6.30 and later.
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
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# NDIS_SWITCH_DEREFERENCE_SWITCH_PORT function
The <i>DereferenceSwitchPort</i> function decrements the Hyper-V extensible switch reference counter for an extensible switch port. The reference counter was incremented through a previous call to <a href="https://msdn.microsoft.com/5FD2E931-AC9F-4157-9C45-F93261FC834D">ReferenceSwitchPort</a>.

## Syntax

```
NDIS_SWITCH_DEREFERENCE_SWITCH_PORT NdisSwitchDereferenceSwitchPort;

NDIS_STATUS NdisSwitchDereferenceSwitchPort(
  NDIS_SWITCH_CONTEXT NdisSwitchContext,
  NDIS_SWITCH_PORT_ID SwitchPortId
)
{...}
```

## Parameters

`NdisSwitchContext`

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.

`SwitchPortId`

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port for which the extensible switch reference counter is incremented.


## Return Value

If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.

## Remarks

The extensible switch extension calls <i>DereferenceSwitchPort</i> to decrement the reference counter for an extensible switch port. While the extensible switch reference counter has a nonzero value, the protocol edge of the extensible switch will not issue an object identifier (OID) set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598273">OID_SWITCH_PORT_DELETE</a> to delete the port.

The extension must call <i>DereferenceSwitchPort</i> if it had previously called <a href="https://msdn.microsoft.com/5FD2E931-AC9F-4157-9C45-F93261FC834D">ReferenceSwitchPort</a> for an extensible switch port.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>

<a href="https://msdn.microsoft.com/5FD2E931-AC9F-4157-9C45-F93261FC834D">ReferenceSwitchPort</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598273">OID_SWITCH_PORT_DELETE</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_DEREFERENCE_SWITCH_PORT callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>