---
UID: NC:d3dkmddi.DXGKDDI_CALIBRATEGPUCLOCK
title: DXGKDDI_CALIBRATEGPUCLOCK
author: windows-driver-content
description: Called by the Microsoft DirectX graphics kernel subsystem to calibrate the GPU time stamps in the DXGK_HISTORY_BUFFER history buffer with the CPU clock time.
old-location: display\dxgkddicalibrategpuclock.htm
old-project: display
ms.assetid: AF912508-D6EF-450D-AEC3-47D1C44D0DA0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_CALIBRATEGPUCLOCK, DxgkDdiCalibrateGpuClock, DxgkDdiCalibrateGpuClock callback function [Display Devices], d3dkmddi/DxgkDdiCalibrateGpuClock, display.dxgkddicalibrategpuclock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkDdiCalibrateGpuClock
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_CALIBRATEGPUCLOCK callback function
Called by the  Microsoft DirectX graphics kernel subsystem to calibrate the GPU time stamps in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn439361">DXGK_HISTORY_BUFFER</a> history buffer with the CPU clock time.

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

The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.

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
| **Windows version** | Windows 8.1,WDDM 1.3 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn467320">DXGKARG_CALIBRATEGPUCLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn439361">DXGK_HISTORY_BUFFER</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>