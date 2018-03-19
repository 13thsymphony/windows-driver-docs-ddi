---
UID: NF:wdm.MmIsDriverVerifying
title: MmIsDriverVerifying function
author: windows-driver-content
description: The MmIsDriverVerifying routine indicates whether the kernel-mode driver that is identified by the specified driver object is being verified or calls a driver that is being verified by Driver Verifier.
old-location: kernel\mmisdriververifying.htm
old-project: kernel
ms.assetid: 74bfe9fb-f751-46a6-a95b-f715ebedd2ec
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: MmIsDriverVerifying, MmIsDriverVerifying routine [Kernel-Mode Driver Architecture], k106_50d610e1-b3ae-41c5-a696-13ab0cf314b6.xml, kernel.mmisdriververifying, wdm/MmIsDriverVerifying
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmIsDriverVerifying
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmIsDriverVerifying function
The <b>MmIsDriverVerifying</b> routine indicates whether the kernel-mode driver that is identified by the specified <a href="https://msdn.microsoft.com/497ee2dc-671d-408e-b228-16dc24532375">driver object</a> is being verified or calls a driver that is being verified by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a>.

## Syntax

````
LOGICAL MmIsDriverVerifying(
  _In_ struct _DRIVER_OBJECT *DriverObject
);
````

## Parameters

`DriverObject`

A pointer to a <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure that represents a driver object. The driver receives this pointer as an input parameter to its <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine.


## Return Value

<b>MmIsDriverVerifying</b> returns <b>TRUE</b> if the specified driver either is in the driver verification list or imports calls to entry points in a driver that is in the driver verification list. Otherwise, this routine returns <b>FALSE</b>.

## Remarks

A kernel-mode driver can call this routine to determine whether it is being monitored by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a>. Driver Verifier monitors kernel-mode drivers to detect illegal function calls or actions that might corrupt the system. To select drivers to be verified, you can use the <a href="https://msdn.microsoft.com/7cdf5277-7187-4e90-b22a-6f828f06e2fb">Verifier Command Line</a> or <a href="https://msdn.microsoft.com/37a7d348-8b55-44f7-86d6-6b195704b9fd">Driver Verifier Manager</a>. For more information about adding drivers to the driver verification list, see <a href="https://msdn.microsoft.com/a752dea1-f49c-4e58-9e56-6b54701c760e">Selecting Drivers to be Verified</a>.

A similar routine, <a href="..\wdm\nf-wdm-mmisdriververifyingbyaddress.md">MmIsDriverVerifyingByAddress</a>, indicates whether a driver identified by a driver image address is being verified or calls a driver that is being verified. <b>MmIsDriverVerifyingByAddress</b> is available starting with Windows Vista.

Another related routine, <a href="..\wdm\nf-wdm-mmisdriversuspectforverifier.md">MmIsDriverSuspectForVerifier</a>, indicates whether a driver represented by a <a href="https://msdn.microsoft.com/497ee2dc-671d-408e-b228-16dc24532375">driver object</a> is in the list of drivers that are selected to be verified. <b>MmIsDriverSuspectForVerifier</b> is available starting with Windows 8.

For example, if driver A has an import table through which it calls one or more entry points in driver B, and driver B is in the driver verification list, then <code>MmIsDriverVerifying(A)</code> returns <b>TRUE</b> and <code>MmIsDriverSuspectForVerifier(B)</code> returns <b>TRUE</b>. If driver A is not in the driver verification list, <code>MmIsDriverSuspectForVerifier(A)</code> returns <b>FALSE</b>. Even if driver B does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifying(B)</code> returns <b>TRUE</b> because driver B is in the driver verification list. If a driver C is not in the driver verification list and does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifying(C)</code> and <code>MmIsDriverSuspectForVerifier(C)</code> both return <b>FALSE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a>



<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>



<a href="..\wdm\nf-wdm-mmisdriververifyingbyaddress.md">MmIsDriverVerifyingByAddress</a>