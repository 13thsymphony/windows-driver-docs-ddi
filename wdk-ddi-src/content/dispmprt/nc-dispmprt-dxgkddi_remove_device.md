---
UID : NC:dispmprt.DXGKDDI_REMOVE_DEVICE
title : DXGKDDI_REMOVE_DEVICE
author : windows-driver-content
description : The DxgkDdiRemoveDevice function frees any resources allocated during DxgkDdiAddDevice.
old-location : display\dxgkddiremovedevice.htm
old-project : display
ms.assetid : 0d5f96e8-dcb3-49e5-8347-ba20d757618b
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.dxgkddiremovedevice, DxgkDdiRemoveDevice callback function [Display Devices], DxgkDdiRemoveDevice, DXGKDDI_REMOVE_DEVICE, DXGKDDI_REMOVE_DEVICE, dispmprt/DxgkDdiRemoveDevice, DmFunctions_b8ab26af-93dd-4e49-b2a2-9c620678457d.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : dispmprt.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---


# DXGKDDI_REMOVE_DEVICE function
The <i>DxgkDdiRemoveDevice</i> function frees any resources allocated during <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>.

## Syntax

```
DXGKDDI_REMOVE_DEVICE DxgkddiRemoveDevice;

NTSTATUS DxgkddiRemoveDevice(
  IN_CONST_PVOID MiniportDeviceContext
)
{...}
```

## Parameters

`MiniportDeviceContext`

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


## Return Value

<i>DxgkDdiRemoveDevice </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## Remarks

<i>DxgkDdiRemoveDevice</i> must free the context block represented by <i>MiniportDeviceContext</i>.

<i>DxgkDdiRemoveDevice</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dispmprt.h |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_REMOVE_DEVICE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>