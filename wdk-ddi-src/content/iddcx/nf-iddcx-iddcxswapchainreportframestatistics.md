---
UID: NF:iddcx.IddCxSwapChainReportFrameStatistics
title: IddCxSwapChainReportFrameStatistics function
author: windows-driver-content
description: An OS callback function the driver calls to report the frame statistics after it has processed a frame completely.
old-location: display\iddcxswapchainreportframestatistics.htm
old-project: display
ms.assetid: 0dd32160-93d4-4fb8-aed1-9267f38e9909
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.iddcxswapchainreportframestatistics, IddCxSwapChainReportFrameStatistics, iddcx/IddCxSwapChainReportFrameStatistics, IddCxSwapChainReportFrameStatistics method [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "_Must_inspect_result_"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IddCxSwapChainReportFrameStatistics
product: Windows
targetos: Windows
req.typenames: 
---


# IddCxSwapChainReportFrameStatistics function
An OS callback function the driver calls to report the frame statistics after it has processed a frame completely

## Syntax

````
NTSTATUS IddCxSwapChainReportFrameStatistics(
  _In_       IDDCX_SWAPCHAIN                 SwapChainObject,
  _In_ const IDARG_IN_REPORTFRAMESTATISTICS* pInArgs
);
````

## Parameters

`SwapChainObject`

The swap-chain object whose current frame is being queried.

`pInArgs`

Input arguments to the function


## Return Value

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | iddcx.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | "_Must_inspect_result_" |