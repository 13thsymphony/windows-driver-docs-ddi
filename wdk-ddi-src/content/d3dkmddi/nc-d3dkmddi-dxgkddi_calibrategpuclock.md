---
UID : NC:d3dkmddi.DXGKDDI_CALIBRATEGPUCLOCK
title : DXGKDDI_CALIBRATEGPUCLOCK
author : windows-driver-content
description : Called by the Microsoft DirectX graphics kernel subsystem to calibrate the GPU time stamps in the DXGK_HISTORY_BUFFER history buffer with the CPU clock time.
old-location : display\dxgkddicalibrategpuclock.htm
old-project : display
ms.assetid : AF912508-D6EF-450D-AEC3-47D1C44D0DA0
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dkmddi.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 8.1,WDDM 1.3
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DxgkDdiCalibrateGpuClock
req.alt-loc : D3dkmddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : DISPATCH_LEVEL
req.typenames : DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_CALIBRATEGPUCLOCK function
Called by the  Microsoft DirectX graphics kernel subsystem to calibrate the GPU time stamps in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_history_buffer.md">DXGK_HISTORY_BUFFER</a> history buffer with the CPU clock time.

## Syntax

```
DXGKDDI_CALIBRATEGPUCLOCK DxgkddiCalibrategpuclock;

NTSTATUS DxgkddiCalibrategpuclock(
  IN_CONST_HANDLE hAdapter,
  IN UINT32 NodeOrdinal,
  IN UINT32 EngineOrdinal,
  OUT_PDXGKARG_CALIBRATEGPUCLOCK pClockCalibration
)
{...}
```

## Parameters

`hAdapter`

A handle to the adapter object for the GPU for which timing calibration info is to be obtained. 

The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

`NodeOrdinal`

An index of a node for which timing calibration info will be obtained. This node is within the physical adapter defined by the <i>hAdapter</i> parameter.

`EngineOrdinal`

The zero-based index of the engine, within the node that <i>NodeOrdinal</i> specifies, for which timing calibration info will be obtained. For graphics adapters that are not part of a link in a linked display adapter (LDA) configuration, you should always set <i>EngineOrdinal</i> to 0.

`pClockCalibration`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn467320">DXGKARG_CALIBRATEGPUCLOCK</a> structure that provides clock counter info from the GPU and CPU.


## Return Value

Returns <b>STATUS_SUCCESS</b> if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## Remarks

The DirectX graphics kernel subsystem uses the returned info in the <i>pClockCalibration</i> parameter to estimate the drift between the GPU and CPU clocks.

To minimize calibration inaccuracies, the driver should compute the values for the <b>GpuClockCounter</b>
  and <b>CpuClockCounter</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn467320">DXGKARG_CALIBRATEGPUCLOCK</a> structure as nearly simultaneously as possible.

The DirectX graphics kernel subsystem calls this function often enough, typically at least once every 30ms, to minimize the accumulated drift between the GPU and CPU clocks.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_history_buffer.md">DXGK_HISTORY_BUFFER</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn467320">DXGKARG_CALIBRATEGPUCLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CALIBRATEGPUCLOCK callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>