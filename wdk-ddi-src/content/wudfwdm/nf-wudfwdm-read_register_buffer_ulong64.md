---
UID: NF:wudfwdm.READ_REGISTER_BUFFER_ULONG64
title: READ_REGISTER_BUFFER_ULONG64 function
author: windows-driver-content
description: The READ_REGISTER_BUFFER_ULONG64 function reads a number of ULONG64 values from the specified register address into a buffer.
old-location: wdf\read_register_buffer_ulong64.htm
old-project: wdf
ms.assetid: 8961126F-FE54-4369-A929-6CC4BDC67598
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: READ_REGISTER_BUFFER_ULONG64 function, umdf.read_register_buffer_ulong64, READ_REGISTER_BUFFER_ULONG64, wudfddi_hwaccess/READ_REGISTER_BUFFER_ULONG64, wdf.read_register_buffer_ulong64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfwdm.h
req.include-header: Wdm.h, Miniport.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: 64-bit Windows
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi_hwaccess.h
apiname:
-	READ_REGISTER_BUFFER_ULONG64
product: Windows
targetos: Windows
req.typenames: "*PPO_FX_PERF_STATE_UNIT, PO_FX_PERF_STATE_UNIT"
req.product: Windows 10 or later.
---


# READ_REGISTER_BUFFER_ULONG64 function
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>READ_REGISTER_BUFFER_ULONG64</b> function reads a number of ULONG64 values from the specified register address into a buffer.

## Syntax

````
void READ_REGISTER_BUFFER_ULONG64(
  _In_  IWDFDevice3 *pDevice,
  _In_  PULONG64    Register,
  _Out_ PULONG64    Buffer,
  _In_  ULONG       Count 
);
````

## Parameters

`Register`

A pointer to the register, which must be a mapped range in memory space.

`Buffer`

A pointer to a buffer into which an array of ULONG64 values is read.

`Count`

Specifies the number of ULONG64 values to be read into the buffer.


## Return Value

This function does not return a value.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/A0640E60-B0DF-4CAD-B292-CC1875EF7F7D">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | 64-bit Windows  |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfwdm.h (include Wdm.h, Miniport.h, Wudfwdm.h) |
| **Library** | NtosKrnl.exe |