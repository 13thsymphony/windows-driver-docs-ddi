---
UID : NF:wdm.ExIsProcessorFeaturePresent
title : ExIsProcessorFeaturePresent function
author : windows-driver-content
description : The ExIsProcessorFeaturePresent routine queries for the existence of a specified processor feature.
old-location : kernel\exisprocessorfeaturepresent.htm
old-project : kernel
ms.assetid : d8c4d1d7-3510-48c4-b1a6-062157f4632e
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : k102_4dccea04-24a3-4465-97bc-67bb58cee3b1.xml, wdm/ExIsProcessorFeaturePresent, ExIsProcessorFeaturePresent routine [Kernel-Mode Driver Architecture], ExIsProcessorFeaturePresent, kernel.exisprocessorfeaturepresent
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : IrqlExPassive, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ExIsProcessorFeaturePresent function
The <b>ExIsProcessorFeaturePresent</b> routine queries for the existence of a specified processor feature.

## Syntax

````
BOOLEAN ExIsProcessorFeaturePresent(
  _In_ ULONG ProcessorFeature
);
````

## Parameters

`ProcessorFeature`

Specifies one of the following constant values:




#### PF_3DNOW_INSTRUCTIONS_AVAILABLE

The processor supports AMD 3DNow instructions.


#### PF_COMPARE64_EXCHANGE128

The atomic compare 64-bit and exchange 128-bit operation (CMP8XCHG16) is available. This parameter value is supported only in Windows Vista and later versions of Windows.


#### PF_COMPARE_EXCHANGE128

The atomic compare and exchange 128-bit operation (CMPXCHG16B) is available. This parameter value is supported only in Windows Vista and later versions of Windows.


#### PF_COMPARE_EXCHANGE_DOUBLE

The processor has an 8-byte, memory-locked compare and exchange (CMPXCHG8B) instruction.


#### PF_FLOATING_POINT_EMULATED

The processor does not have floating-point hardware.


#### PF_FLOATING_POINT_PRECISION_ERRATA

The processor has the Pentium floating-point divide bug.


#### PF_MMX_INSTRUCTIONS_AVAILABLE

The processor supports MMX instructions in hardware.


#### PF_NX_ENABLED

<a href="http://go.microsoft.com/fwlink/p/?linkid=165498">Data execution prevention</a> is enabled. This parameter value is supported only in Windows Vista and later versions of Windows.


#### PF_PAE_ENABLED

The processor implements Physical Address Extension (PAE) support.


#### PF_RDTSC_INSTRUCTION_AVAILABLE

The processor supports a read-timestamp-counter (RDTSC) instruction.


#### PF_SSE3_INSTRUCTIONS_AVAILABLE

The processor supports SSE3 instructions. This parameter value is supported only in Windows Vista and later versions of Windows.


#### PF_SSE_DAZ_MODE_AVAILABLE

The processor supports the denormals-are-zero (DAZ) mode for SSE instructions. This parameter value is supported only in Windows Vista and later versions of Windows.


#### PF_XMMI64_INSTRUCTIONS_AVAILABLE

The processor supports SSE2 instructions in hardware. This parameter value is supported only in Windows XP and later versions of Windows.


#### PF_XMMI_INSTRUCTIONS_AVAILABLE

The processor supports SSE instructions in hardware.


#### PF_XSAVE_ENABLED

The processor supports the XSAVE and XRSTOR instructions. This parameter value is supported only in Windows 7 and later versions of Windows.


## Return Value

<b>ExIsProcessorFeaturePresent</b> returns <b>TRUE</b> if the specified processor feature is present; otherwise, it returns <b>FALSE</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlExPassive, PowerIrpDDis, HwStorPortProhibitedDDIs |