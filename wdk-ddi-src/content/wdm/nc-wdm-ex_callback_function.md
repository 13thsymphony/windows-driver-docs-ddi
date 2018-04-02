---
UID: NC:wdm.EX_CALLBACK_FUNCTION
title: EX_CALLBACK_FUNCTION
author: windows-driver-content
description: A filter driver's RegistryCallback routine can monitor, block, or modify a registry operation.
old-location: kernel\registrycallback.htm
old-project: kernel
ms.assetid: 220ce3b8-2820-4753-9659-5ce7b4f4f32d
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: DrvrRtns_988f8f3d-4ee8-4351-8fc0-703a88bd8421.xml, EX_CALLBACK_FUNCTION, RegistryCallback, RegistryCallback routine [Kernel-Mode Driver Architecture], kernel.registrycallback, wdm/RegistryCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows XP (see Return Value section).
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
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL (see Remarks section).
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	RegistryCallback
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# EX_CALLBACK_FUNCTION callback function
A filter driver's <i>RegistryCallback</i> routine can monitor, block, or modify a registry operation.

## Syntax

```
EX_CALLBACK_FUNCTION ExCallbackFunction;

NTSTATUS ExCallbackFunction(
  PVOID CallbackContext,
  PVOID Argument1,
  PVOID Argument2
)
{...}
```

## Parameters

`CallbackContext`

The value that the driver passed as the <i>Context</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541918">CmRegisterCallback</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541921">CmRegisterCallbackEx</a> when it registered this <i>RegistryCallback</i> routine.

`Argument1`

A <a href="https://msdn.microsoft.com/2ec47d47-1de3-43af-9a71-7fa366ba2d1a">REG_NOTIFY_CLASS</a>-typed value that identifies the type of registry operation that is being performed and whether the <i>RegistryCallback</i> routine is being called before or after the registry operation is performed.

`Argument2`

A pointer to a structure that contains information that is specific to the type of registry operation. The structure type depends on the REG_NOTIFY_CLASS-typed value for <i>Argument1</i>, as shown in the following table. For information about which REG_NOTIFY_CLASS-typed values are available for which operating system versions, see <a href="https://msdn.microsoft.com/2ec47d47-1de3-43af-9a71-7fa366ba2d1a">REG_NOTIFY_CLASS</a>.

<table>
<tr>
<th>REG_NOTIFY_CLASS Value</th>
<th>Structure Type</th>
</tr>
<tr>
<td><b>RegNtDeleteKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560926">REG_DELETE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreDeleteKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560926">REG_DELETE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostDeleteKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtSetValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561016">REG_SET_VALUE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreSetValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561016">REG_SET_VALUE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostSetValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtDeleteValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560929">REG_DELETE_VALUE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreDeleteValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560929">REG_DELETE_VALUE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostDeleteValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtSetInformationKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561009">REG_SET_INFORMATION_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreSetInformationKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561009">REG_SET_INFORMATION_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostSetInformationKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtRenameKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560994">REG_RENAME_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreRenameKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560994">REG_RENAME_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostRenameKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtEnumerateKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560932">REG_ENUMERATE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreEnumerateKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560932">REG_ENUMERATE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostEnumerateKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtEnumerateValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560936">REG_ENUMERATE_VALUE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreEnumerateValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560936">REG_ENUMERATE_VALUE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostEnumerateValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtQueryKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560980">REG_QUERY_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreQueryKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560980">REG_QUERY_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostQueryKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtQueryValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560991">REG_QUERY_VALUE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreQueryValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560991">REG_QUERY_VALUE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostQueryValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtQueryMultipleValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560985">REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreQueryMultipleValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560985">REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostQueryMultipleValueKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreCreateKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560973">REG_PRE_CREATE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreCreateKeyEx</b></td>
<td>
<a href="https://msdn.microsoft.com/5609a2c4-71db-432a-8a39-e407130a6e4c">REG_CREATE_KEY_INFORMATION**</a>
</td>
</tr>
<tr>
<td><b>RegNtPostCreateKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560962">REG_POST_CREATE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostCreateKeyEx</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreOpenKey</b></td>
<td>
<a href="https://msdn.microsoft.com/9b7240b5-429b-4bf2-aa7b-373b63bb79ae">REG_PRE_OPEN_KEY_INFORMATION**</a>
</td>
</tr>
<tr>
<td><b>RegNtPreOpenKeyEx</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560957">REG_OPEN_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostOpenKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560967">REG_POST_OPEN_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostOpenKeyEx</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtKeyHandleClose</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560943">REG_KEY_HANDLE_CLOSE_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreKeyHandleClose</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560943">REG_KEY_HANDLE_CLOSE_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostKeyHandleClose</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreFlushKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560938">REG_FLUSH_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostFlushKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreLoadKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560948">REG_LOAD_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostLoadKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreUnLoadKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561018">REG_UNLOAD_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostUnLoadKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreQueryKeySecurity</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560983">REG_QUERY_KEY_SECURITY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostQueryKeySecurity</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreSetKeySecurity</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561012">REG_SET_KEY_SECURITY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostSetKeySecurity</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtCallbackObjectContextCleanup</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560919">REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreRestoreKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561002">REG_RESTORE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostRestoreKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561002">REG_RESTORE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreSaveKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561005">REG_SAVE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostSaveKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561005">REG_SAVE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreReplaceKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560998">REG_REPLACE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPostReplaceKey</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560998">REG_REPLACE_KEY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>RegNtPreQueryKeyName</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt661826">REG_QUERY_KEY_NAME</a>
</td>
</tr>
<tr>
<td><b>RegNtPostQueryKeyName</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560971">REG_POST_OPERATION_INFORMATION</a>
</td>
</tr>
</table>
 

** Starting with Windows 7, the actual data structure passed in when the notify class is <b>RegNtPreCreateKeyEx</b> or <b>RegNtPreOpenKeyEx</b> is the V1 version of this structure, <a href="https://msdn.microsoft.com/library/windows/hardware/ff560922">REG_CREATE_KEY_INFORMATION_V1</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff560959">REG_OPEN_KEY_INFORMATION_V1</a>, respectively. Check the <b>Reserved</b> member to determine the version of the structure.

<table>
<tr>
<th>Version number</th>
<th>Structure name</th>
</tr>
<tr>
<td>0</td>
<td><b>REG_CREATE_KEY_INFORMATION</b> and <b>REG_OPEN_KEY_INFORMATION</b></td>
</tr>
<tr>
<td>1</td>
<td><b>REG_CREATE_KEY_INFORMATION_V1</b> and <b>REG_OPEN_KEY_INFORMATION_V1</b></td>
</tr>
</table>


## Return Value

For more information about when a <i>RegistryCallback</i> routine should return each of these status values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.

## Remarks

To be notified of registry operations, a kernel-mode component (such as the driver component of an antivirus software package) can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541918">CmRegisterCallback</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541921">CmRegisterCallbackEx</a> to register a <i>RegistryCallback</i> routine.

The <i>RegistryCallback</i> routine can inspect the contents of the input and output buffers that are supplied for registry operations. A registry operation can be initiated by a user-mode application that calls a user-mode registry routine (such as <a href="https://msdn.microsoft.com/e9ffad7f-c0b6-44ce-bf22-fbe45ca98bf4">RegCreateKeyEx</a> or <a href="https://msdn.microsoft.com/c8a590f2-3249-437f-a320-c7443d42b792">RegOpenKeyEx</a>) or by a driver that calls a kernel-mode registry routine (such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>). An <i>input buffer</i> is a memory buffer supplied by the initiator from which the registry reads input data for the operation. An <i>output buffer</i> is a buffer supplied by the initiator into which the registry writes output data requested by the initiator.

Before calling the <i>RegistryCallback</i> routine, the kernel probes (to verify alignment and accessibility) all members of the <i>Argument2</i> structures that point to output buffers in user-mode memory, but does not capture user-mode output buffers in system memory. The callback routine must enclose any access of an output buffer in a <b>try</b>/<b>except</b> block. If the callback routine needs to pass an output buffer pointer to a system routine (for example, <a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>), and the buffer is in user-mode memory, the callback routine must first capture the buffer.

The handling of input buffers depends on the Windows version. Starting with Windows 8, the kernel captures all input buffers pointed to by members of the <i>Argument2</i> structures in system memory before calling the <i>RegistryCallback</i> routine. In versions of Windows before Windows 8, the kernel probes all members of the <i>Argument2</i> structures that point to input buffers in user-mode memory, but captures only some of these buffers in system memory. In these earlier versions of Windows, the callback routine must enclose any access of an input buffer in a <b>try</b>/<b>except</b> block. Additionally, if the callback routine needs to pass an input buffer pointer to a system routine (for example, <b>ZwOpenKey</b>), and the buffer is in user-mode memory, the callback routine must first capture the buffer.

The following table summarizes the requirements for buffer accesses by the <i>RegistryCallback</i> routine.

<table>
<tr>
<th>Buffer type</th>
<th>Windows version</th>
<th>Buffer pointer passed to callback routine</th>
<th>Safe for callback routine to directly access?</th>
<th>Safe to pass to system routines (such as <b>ZwOpenKey</b>)?</th>
</tr>
<tr>
<td>User-mode input</td>
<td>Windows 8 and later</td>
<td>Points to captured data.</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td>User-mode input</td>
<td>Windows 7 and earlier</td>
<td>Points to captured data or original user-mode buffer.</td>
<td>No. Must read under try/except.</td>
<td>No. Must allocate kernel memory, copy data from the original buffer under try/except, and pass the copied data to the system routine.</td>
</tr>
<tr>
<td>User-mode output</td>
<td>All</td>
<td>Points to original user-mode buffer.</td>
<td>No. Must write under try/except.</td>
<td>No. Must allocate kernel memory, pass kernel memory to the system routine, and copy the results back to the original buffer under try/except.</td>
</tr>
<tr>
<td>Kernel-mode input and output</td>
<td>All</td>
<td>Points to original kernel-mode buffer.</td>
<td>Yes</td>
<td>Yes</td>
</tr>
</table>
 

For more information about <i>RegistryCallback</i> routines and registry filter drivers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.

A <i>RegistryCallback</i> executes at IRQL = PASSIVE_LEVEL and in the context of the thread that is performing the registry operation.


#### Examples

To define a <i>RegistryCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>RegistryCallback</i> callback routine that is named <code>MyRegistryCallback</code>, use the EX_CALLBACK_FUNCTION type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EX_CALLBACK_FUNCTION MyRegistryCallback;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS 
  MyRegistryCallback(
    PVOID  CallbackContext,
    PVOID  Argument1,
    PVOID  Argument2 
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The EX_CALLBACK_FUNCTION function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EX_CALLBACK_FUNCTION function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows XP (see Return Value section).  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | Called at PASSIVE_LEVEL (see Remarks section). |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541918">CmRegisterCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541928">CmUnRegisterCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559876">ProbeForRead</a>



<a href="https://msdn.microsoft.com/2ec47d47-1de3-43af-9a71-7fa366ba2d1a">REG_NOTIFY_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>