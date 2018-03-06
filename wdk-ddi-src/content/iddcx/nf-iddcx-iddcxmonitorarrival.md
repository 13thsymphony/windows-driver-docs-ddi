---
UID: NF:iddcx.IddCxMonitorArrival
title: IddCxMonitorArrival function
author: windows-driver-content
description: An OS callback function the driver calls to report a monitor arrival on the WDDM graphics adapter.
old-location: display\iddcxmonitorarrival.htm
old-project: display
ms.assetid: e73a8111-9e54-4040-a38a-441948e10212
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IddCxMonitorArrival, IddCxMonitorArrival method [Display Devices], display.iddcxmonitorarrival, iddcx/IddCxMonitorArrival
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IddCxMonitorArrival
product: Windows
targetos: Windows
req.typenames: 
---


# IddCxMonitorArrival function
An OS callback function the driver calls to report a monitor arrival on the WDDM graphics adapter

## Syntax

````
NTSTATUS IddCxMonitorArrival(
  _In_  IDDCX_MONITOR             AdapterObject,
  _Out_ IDARG_OUT_MONITORARRIVAL* pOutArgs
);
````

## Parameters

`AdapterObject`

The adapter object that is hosting the newly arrived monitor

`pOutArgs`

Output arguments to the function


## Return Value

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | iddcx.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | "_Must_inspect_result_" |