---
UID: NF.wdfverifier.WdfVerifierKeBugCheck
title: WdfVerifierKeBugCheck function
author: windows-driver-content
description: The WdfVerifierKeBugCheck function creates a bug check.
old-location: wdf\wdfverifierkebugcheck.htm
old-project: wdf
ms.assetid: 3fa8ea3d-cca0-402d-a3a8-1281ad4231d4
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfVerifierKeBugCheck
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfverifier.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfVerifierKeBugCheck
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
req.product: Windows 10 or later.
---

# WdfVerifierKeBugCheck function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfVerifierKeBugCheck</b> function creates a bug check.


## -syntax

````
VOID WdfVerifierKeBugCheck(
  _In_ ULONG     BugCheckCode,
  _In_ ULONG_PTR BugCheckParameter1,
  _In_ ULONG_PTR BugCheckParameter2,
  _In_ ULONG_PTR BugCheckParameter3,
  _In_ ULONG_PTR BugCheckParameter4
);
````


## -parameters

### -param BugCheckCode [in]

One of the <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a> that are defined in <i>Bugcodes.h</i>.

### -param BugCheckParameter1 [in]

For information about this parameter, see the specified bug check code's description.

### -param BugCheckParameter2 [in]

For information about this parameter, see the specified bug check code's description.

### -param BugCheckParameter3 [in]

For information about this parameter, see the specified bug check code's description.

### -param BugCheckParameter4 [in]

For information about this parameter, see the specified bug check code's description.

## -returns
None

## -remarks
If your Kernel-Mode Driver Framework (KMDF) driver calls <b>WdfVerifierKeBugCheck</b>, the operating system halts and displays a <a href="https://msdn.microsoft.com/8cc42643-e231-49dd-96b0-6cb528d5d7a9">blue screen</a> unless a <a href="https://msdn.microsoft.com/e2490442-9d90-454b-95e0-db8c5d7fa19a">debugger</a> is running.

If your  User-Mode Driver Framework (UMDF) driver (version 2.0 or later) calls <b>WdfVerifierKeBugCheck</b>, the framework does not use  the parameters that the driver supplies.   In this case, the framework breaks into the debugger if one is connected. If a debugger is not connected, the framework generates an exception, and the default UMDF exception handler creates a minidump file. For more information about unhandled exceptions in the driver host process, see <a href="wdf.how_umdf_reports_errors">How UMDF Reports Errors</a>.

For more information about debugging your driver, see <a href="wdf.debugging_a_wdf_driver">Debugging WDF Drivers</a>.

The following code example creates a bug check that uses the <a href="https://msdn.microsoft.com/bc60b4b3-aded-4c67-bbaa-aad1b6b38d30">MULTIPLE_IRP_COMPLETE_REQUESTS</a> bug check code.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfverifier.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Any level
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfverifierdbgbreakpoint">WdfVerifierDbgBreakPoint</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfVerifierKeBugCheck function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
