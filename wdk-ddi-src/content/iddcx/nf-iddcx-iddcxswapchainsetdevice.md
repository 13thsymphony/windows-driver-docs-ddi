---
UID: NF:iddcx.IddCxSwapChainSetDevice
title: IddCxSwapChainSetDevice function
author: windows-driver-content
description: An OS callback function the driver calls within its SetSwapChain routine to setup the swap-chain with a particular DXGI device.
old-location: display\iddcxswapchainsetdevice.htm
old-project: display
ms.assetid: f1e96d8a-910e-4808-b9a3-e8c530158872
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IddCxSwapChainSetDevice, IddCxSwapChainSetDevice method [Display Devices], iddcx/IddCxSwapChainSetDevice, display.iddcxswapchainsetdevice
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
-	IddCxSwapChainSetDevice
product: Windows
targetos: Windows
req.typenames: 
---


# IddCxSwapChainSetDevice function
An OS callback function the driver calls within its SetSwapChain routine to setup the swap-chain with a particular DXGI device.

## Syntax

````
HRESULT IddCxSwapChainSetDevice(
  _In_ IDDCX_SWAPCHAIN              SwapChainObject,
  _In_ IDARG_IN_SWAPCHAINSETDEVICE* pInArgs
);
````

## Parameters

`SwapChainObject`

The swap-chain object that will be setup with a particular DXGI device.

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