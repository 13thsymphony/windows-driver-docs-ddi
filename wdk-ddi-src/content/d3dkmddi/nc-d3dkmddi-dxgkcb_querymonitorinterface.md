---
UID: NC:d3dkmddi.DXGKCB_QUERYMONITORINTERFACE
title: DXGKCB_QUERYMONITORINTERFACE
author: windows-driver-content
description: The DxgkCbQueryMonitorInterface function returns a pointer to a DXGK_MONITOR_INTERFACE structure.
old-location: display\dxgkcbquerymonitorinterface.htm
old-project: display
ms.assetid: 0c23e72d-3eb9-4511-a386-1dcc2f4910b7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKCB_QUERYMONITORINTERFACE, DpFunctions_6d1b7fa2-c5ab-4fd0-8a60-740c5415777c.xml, DxgkCbQueryMonitorInterface, DxgkCbQueryMonitorInterface callback function [Display Devices], d3dkmddi/DxgkCbQueryMonitorInterface, display.dxgkcbquerymonitorinterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkCbQueryMonitorInterface
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKCB_QUERYMONITORINTERFACE callback function
The <b>DxgkCbQueryMonitorInterface</b> function returns a pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface.md">DXGK_MONITOR_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to obtain other interfaces that provide access to monitor descriptors, modes, and frequency ranges.

## Syntax

```
DXGKCB_QUERYMONITORINTERFACE DxgkcbQuerymonitorinterface;

NTSTATUS DxgkcbQuerymonitorinterface(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_DXGK_MONITOR_INTERFACE_VERSION MonitorInterfaceVersion,
  DEREF_OUT_CONST_PPDXGK_MONITOR_INTERFACE ppMonitorInterface
)
{...}
```

## Parameters

`hAdapter`

[in] A handle that represents a display adapter. The VidPN manager provided this handle to the display miniport driver in a call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>, or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a>.

`MonitorInterfaceVersion`

[in] A value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_monitor_interface_version.md">DXGK_MONITOR_INTERFACE_VERSION</a> enumeration that specifies the version of the monitor interface being requested.

`ppMonitorInterface`

[out] A pointer to a variable that receives a pointer to the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface.md">DXGK_MONITOR_INTERFACE</a> structure.


## Return Value

<b>DxgkCbQueryMonitorInterface</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.</i>h.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include Dispmprt.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor Interface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_QUERYMONITORINTERFACE callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>