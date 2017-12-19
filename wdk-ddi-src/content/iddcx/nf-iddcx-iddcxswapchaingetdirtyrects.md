---
UID: NF.iddcx.IddCxSwapChainGetDirtyRects
title: IddCxSwapChainGetDirtyRects function
author: windows-driver-content
description: An OS callback function the driver calls when it wants retrieve the dirty rects for the current frame.
old-location: display\iddcxswapchaingetdirtyrects.htm
old-project: display
ms.assetid: 4ffe3c46-f729-4088-b69e-f39bc00f40a6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IddCxSwapChainGetDirtyRects
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
req.alt-api: IddCxSwapChainGetDirtyRects
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _Must_inspect_result_
---

# IddCxSwapChainGetDirtyRects function



## -description


                An OS callback function the driver calls when it wants retrieve the dirty rects for the current frame



## -syntax

````
HRESULT IddCxSwapChainGetDirtyRects(
  _In_        IDDCX_SWAPCHAIN          SwapChainObject,
  _In_  const IDARG_IN_GETDIRTYRECTS*  pInArgs,
  _Out_       IDARG_OUT_GETDIRTYRECTS* pOutArgs
);
````


## -parameters

### -param SwapChainObject [in]

The swap-chain object whose current frame is being queried.


### -param pInArgs [in]

Input arguments of the function


### -param pOutArgs [out]

Output  arguments of the function


## -returns

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
_Must_inspect_result_

</td>
</tr>
</table>