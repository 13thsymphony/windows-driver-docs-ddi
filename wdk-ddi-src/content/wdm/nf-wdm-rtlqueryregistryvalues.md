---
UID: NF.wdm.RtlQueryRegistryValues
title: RtlQueryRegistryValues
author: windows-driver-content
description: The RtlQueryRegistryValues routine allows the caller to query several values from the registry subtree with a single call.
old-location: kernel\rtlqueryregistryvalues.htm
old-project: kernel
ms.assetid: 6c6d0664-0c00-461b-bcac-13070511430c
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlQueryRegistryValues
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
req.alt-api: RtlQueryRegistryValues
req.alt-loc: Ntoskrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# RtlQueryRegistryValues function



## -description
<p>The <b>RtlQueryRegistryValues</b> routine allows the caller to query several values from the registry subtree with a single call.</p>


## -syntax

````
NTSTATUS RtlQueryRegistryValues(
  _In_     ULONG                     RelativeTo,
  _In_     PCWSTR                    Path,
  _Inout_  PRTL_QUERY_REGISTRY_TABLE QueryTable,
  _In_opt_ PVOID                     Context,
  _In_opt_ PVOID                     Environment
);
````


## -parameters
<dl>

### -param <i>RelativeTo</i> [in]

<dd>
<p>Specifies whether <i>Path</i> is an absolute registry path or is relative to a predefined path as one of the following.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>RTL_REGISTRY_ABSOLUTE</p>
</td>
<td>
<p>Path is an absolute registry path.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_REGISTRY_CONTROL</p>
</td>
<td>
<p>Path is relative to <b>\Registry\Machine\System\CurrentControlSet\Control</b>.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_REGISTRY_DEVICEMAP</p>
</td>
<td>
<p>Path is relative to <b>\Registry\Machine\Hardware\DeviceMap</b>.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_REGISTRY_SERVICES</p>
</td>
<td>
<p>Path is relative to <b>\Registry\Machine\System\CurrentControlSet\Services</b>.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_REGISTRY_USER</p>
</td>
<td>
<p>Path is relative to <b>\Registry\User\CurrentUser</b>. (For a system process, this is <b>\User\.Default</b>.)</p>
</td>
</tr>
<tr>
<td>
<p>RTL_REGISTRY_WINDOWS_NT</p>
</td>
<td>
<p>Path is relative to <b>\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion</b>.</p>
</td>
</tr>
</table>
<p> </p>
<p>The <i>RelativeTo</i> value can be modified by bitwise-ORing it with one of the following flags.</p>
<table>
<tr>
<td>
<p>RTL_REGISTRY_OPTIONAL</p>
</td>
<td>
<p>Specifies that the key referenced by this parameter and the <i>Path</i> parameter are optional.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_REGISTRY_HANDLE</p>
</td>
<td>
<p>Specifies that the <i>Path</i> parameter is actually a registry handle to use.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>Path</i> [in]

<dd>
<p>Pointer to either an absolute registry path or a path relative to the known location specified by the <i>RelativeTo</i> parameter. Note that the names of keys in such a path must be known to the caller, including the last key in the path. If the RTL_REGISTRY_HANDLE flag is specified, this parameter is a registry handle for an already opened key to be queried directly.</p>
</dd>

### -param <i>QueryTable</i> [in, out]

<dd>
<p>Pointer to a table of one or more value names and subkey names in which the caller is interested. Each table entry contains the address of a caller-supplied <a href="kernel.queryroutine">QueryRoutine</a> function that will be called for each value name that exists in the registry. The table must be terminated with a <b>NULL</b> table entry, which is a table entry with a <b>NULL</b> <b>QueryRoutine</b> member and a <b>NULL</b> <b>Name</b> member. The structure for query table entries is defined as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _RTL_QUERY_REGISTRY_TABLE {
    PRTL_QUERY_REGISTRY_ROUTINE QueryRoutine;
    ULONG Flags;
    PWSTR Name;
    PVOID EntryContext;
    ULONG DefaultType;
    PVOID DefaultData;
    ULONG DefaultLength;
} RTL_QUERY_REGISTRY_TABLE, *PRTL_QUERY_REGISTRY_TABLE;</pre>
</td>
</tr>
</table></span></div>
<p>If the caller allocates storage for the query table pointed to by the <i>QueryTable</i> parameter, the caller is responsible for releasing this storage after the <b>RtlQueryRegistryValues</b> call returns.</p>
<p></p>
<dl>

### -param <a id="QueryRoutine"></a><a id="queryroutine"></a><a id="QUERYROUTINE"></a><b>QueryRoutine</b>

<dd>
<p>The address of a <i>QueryRoutine</i> function that is called with the name, type, data, and data length of a registry value. If this member and the <b>Name</b> member are both <b>NULL</b>, it marks the end of the table.</p>
<p>A <i>QueryRoutine</i> function is declared as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
QueryRoutine (
    IN PWSTR ValueName,
    IN ULONG ValueType,
    IN PVOID ValueData,
    IN ULONG ValueLength,
    IN PVOID Context,
    IN PVOID EntryContext
    );</pre>
</td>
</tr>
</table></span></div>
<p>For more information, see <a href="kernel.queryroutine">QueryRoutine</a>.</p>
</dd>

### -param <a id="Flags"></a><a id="flags"></a><a id="FLAGS"></a><b>Flags</b>

<dd>
<p>Flags to control how the remaining members of the <b>RTL_QUERY_REGISTRY_TABLE</b> structure are to be interpreted. The following flag bits are defined for this member.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>RTL_QUERY_REGISTRY_SUBKEY</p>
</td>
<td>
<p>The <b>Name</b> of this table entry is another path to a registry key, and all following table entries are for that key rather than the key specified by the <i>Path</i> parameter. This change in focus lasts until the end of the table or until another RTL_REGISTRY_SUBKEY or RTL_QUERY_REGISTRY_TOPKEY entry is seen. Each such entry must specify a path that is relative to the <i>Path</i> specified in the call to <b>RtlQueryRegistryValues</b>.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_QUERY_REGISTRY_TOPKEY</p>
</td>
<td>
<p>Resets the current registry key handle to the original one specified by the <i>RelativeTo</i> and <i>Path</i> parameters. This is useful for getting back to the original node after descending into subkeys with the RTL_QUERY_REGISTRY_SUBKEY flag.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_QUERY_REGISTRY_REQUIRED</p>
</td>
<td>
<p>Specifies that this registry value must exist if <b>DefaultType</b> = REG_NONE; otherwise, if it is not found, <b>RtlQueryRegistryValues</b> immediately exits with a status code of STATUS_OBJECT_NAME_NOT_FOUND. This exit occurs if the <b>Name</b> member is <b>NULL</b> and the current key has no subkeys, or if <b>Name</b> specifies a nonexistent subkey. (If this flag is not specified, then when no match is found for a non-<b>NULL</b> <b>Name</b>, the routine uses the <b>DefaultValue</b> member as the value. When <b>Name</b>  is <b>NULL</b> and the current key has no subkeys, the routine simply skips that table entry.)</p>
</td>
</tr>
<tr>
<td>
<p>RTL_QUERY_REGISTRY_NOVALUE</p>
</td>
<td>
<p>Specifies that even though there is no <b>Name</b> for this table entry, all the caller wants is a callback: that is, the caller does <u>not</u> want to enumerate all the values under the current key. <i>QueryRoutine</i> is called with <b>NULL</b> for <i>ValueData</i>, REG_NONE for <i>ValueType</i>, and zero for <i>ValueLength</i>.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_QUERY_REGISTRY_NOEXPAND</p>
</td>
<td>
<p>For a registry value of type REG_EXPAND_SZ or REG_MULTI_SZ, this flag overrides the default behavior, which is to preprocess the registry value before calling the <a href="kernel.queryroutine">QueryRoutine</a> routine. By default, <b>RtlQueryRegistryValues</b> expands environment variable references in REG_EXPAND_SZ values, and enumerates each null-terminated string in a REG_MULTI_SZ value in a separate <i>QueryRoutine</i> call, so that the strings are presented as REG_SZ values that have the same <i>ValueName</i>. If this flag is set, <i>QueryRoutine</i> receives the raw REG_EXPAND_SZ or REG_MULTI_SZ value from the registry. For more information about the data formats for these values, see <a href="..\wdm\ns-wdm--key-value-basic-information.md">KEY_VALUE_BASIC_INFORMATION</a>.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_QUERY_REGISTRY_DIRECT</p>
</td>
<td>
<p>The <b>QueryRoutine</b> member is not used (and must be <b>NULL</b>), and the <i>EntryContext</i> points to the buffer to store the value. If the caller sets this flag, the caller should additionally set the RTL_QUERY_REGISTRY_TYPECHECK flag to guard against buffer overflow. For more information, see the Remarks section.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_QUERY_REGISTRY_TYPECHECK</p>
</td>
<td>
<p>Use this flag with the RTL_QUERY_REGISTRY_DIRECT flag to verify that the REG_<i>XXX</i> type of the stored registry value matches the type expected by the caller. If the types do not match, the call fails. For more information, see the Remarks section.</p>
</td>
</tr>
<tr>
<td>
<p>RTL_QUERY_REGISTRY_DELETE</p>
</td>
<td>
<p>This flag is used to delete value keys after they have been queried.</p>
</td>
</tr>
</table>
<p> </p>
<p>Starting with Windows 2000, inbox support is provided for all flag bits in the preceding table, with the exception of RTL_QUERY_REGISTRY_TYPECHECK. Inbox support for RTL_QUERY_REGISTRY_TYPECHECK is available starting with Windows 8. For earlier versions of Windows, support for RTL_QUERY_REGISTRY_TYPECHECK is provided through Windows Update. For more information, see Remarks.</p>
</dd>

### -param <a id="Name"></a><a id="name"></a><a id="NAME"></a><b>Name</b>

<dd>
<p>This is the name of a Value that the caller queried. If <b>Name</b> is <b>NULL</b>, the <i>QueryRoutine</i> function specified for this table entry is called for all values associated with the current registry key. If the RTL_QUERY_REGISTRY_DIRECT flag is set, a non-<b>NULL</b> value for <b>Name</b> must be provided.</p>
</dd>

### -param <a id="EntryContext"></a><a id="entrycontext"></a><a id="ENTRYCONTEXT"></a><b>EntryContext</b>

<dd>
<p>If the RTL_QUERY_REGISTRY_DIRECT flag is set, this is a pointer to the buffer to store the result of the query operation for this key. Otherwise, this value is passed as the <i>EntryContext</i> parameter of <i>QueryRoutine</i>.</p>
</dd>

### -param <a id="DefaultType"></a><a id="defaulttype"></a><a id="DEFAULTTYPE"></a><b>DefaultType</b>

<dd>
<p>The least significant byte of this member specifies the REG_<i>XXX</i> type of the data to be returned, if no matching key is found and the RTL_QUERY_REGISTRY_REQUIRED flag is not specified. Specify REG_NONE for no default type. If the RTL_QUERY_REGISTRY_TYPECHECK flag is set, the most significant byte of this member specifies the REG_<i>XXX</i> type of the stored registry value that the caller expects. Bits 8 to 23 of this member are reserved and should be zero.</p>
</dd>

### -param <a id="DefaultData"></a><a id="defaultdata"></a><a id="DEFAULTDATA"></a><b>DefaultData</b>

<dd>
<p>A pointer to the default value to be returned if no matching key is found and the RTL_QUERY_REGISTRY_REQUIRED flag is not specified. This member is ignored if <b>DefaultType</b> = REG_NONE. Otherwise, the type of data pointed to by <b>DefaultData</b> should conform to the registry value type specified by the <b>DefaultType</b> member. For more information registry value types, see the definition of the <i>Type</i> parameter in <a href="..\wdm\ns-wdm--key-value-basic-information.md">KEY_VALUE_BASIC_INFORMATION</a>.</p>
</dd>

### -param <a id="DefaultLength"></a><a id="defaultlength"></a><a id="DEFAULTLENGTH"></a><b>DefaultLength</b>

<dd>
<p>Specifies the length, in bytes, of the <b>DefaultData</b> member. If <b>DefaultType</b> is REG_SZ, REG_EXPAND_SZ, or REG_MULTI_SZ, callers can optionally specify zero to indicate <b>RtlQueryRegistryValues</b> should compute the length based on the default data value. If <b>DefaultType</b> = REG_NONE, this member is ignored.</p>
</dd>
</dl>
</dd>

### -param <i>Context</i> [in, optional]

<dd>
<p>Specifies the value passed as the <i>Context</i> parameter of a <i>QueryRoutine</i> function each time it is called.</p>
</dd>

### -param <i>Environment</i> [in, optional]

<dd>
<p>Pointer to the environment used when expanding variable values in REG_EXPAND_SZ registry values, or a <b>NULL</b> pointer (optional).</p>
</dd>
</dl>

## -returns
<p><b>RtlQueryRegistryValues</b> returns an NTSTATUS code. The possible return values include:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The entire query table was processed successfully.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>Processing of the query table terminated with an invalid table entry. A table entry can be invalid if the specified flags require the <b>QueryRoutine</b> or <b>Name</b> member to be non-<b>NULL</b>, but a <b>NULL</b> value was provided.</p><dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl><p>The <i>Path</i> parameter does not match a valid key, or processing of the query table terminated with an entry with the RTL_QUERY_REGISTRY_REQUIRED flag set and no matching key is found. This occurs if the <b>Name</b> member is <b>NULL</b> and the current key has no subkeys, or if <b>Name</b> specifies a nonexistent subkey.</p><dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl><p>The RTL_QUERY_REGISTRY_DIRECT flag is set, and the buffer specified by <b>EntryContext</b> is too small to hold the key value data.</p><dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl><p>The RTL_QUERY_REGISTRY_TYPECHECK flag is set and the type of the stored registry value does not match the type expected by the caller.</p>

<p> </p>

<p><b>RtlQueryRegistryValues</b> also terminates processing of the table if the <i>QueryRoutine</i> function for a table entry returns an NTSTATUS error code, and returns that error code as its result. (With one exception: If <i>QueryRoutine</i> returns STATUS_BUFFER_TOO_SMALL, the error code is ignored.)</p>

## -remarks
<p>The caller specifies an initial key path and a table. The table contains one or more entries that describe the key values and subkey names in which the caller is interested. The table is terminated by an entry with a <b>NULL</b> <b>QueryRoutine</b> member and a <b>NULL</b> <b>Name</b> member. The table must be allocated from nonpaged pool.</p>

<p>If the RTL_QUERY_REGISTRY_TYPECHECK flag is set in a table entry, the caller must specify the expected REG_<i>XXX</i> type in the 8 most significant bits (MSBs) of the 32-bit <b>DefaultType</b> member of the table entry. As shown in the following code example, the RTL_QUERY_REGISTRY_TYPECHECK_SHIFT constant, which is defined to be 24, can be used as the shift count required to place the expected REG_<i>XXX</i> type in the 8 MSBs of the <b>DefaultType</b> member.</p>

<p>Starting with Windows 8, if an <b>RtlQueryRegistryValues</b> call accesses an untrusted hive, and the caller sets the RTL_QUERY_REGISTRY_DIRECT flag for this call, the caller must additionally set the RTL_QUERY_REGISTRY_TYPECHECK flag. A violation of this rule by a call from user mode causes an exception.  A violation of this rule by a call from kernel mode causes a 0x139 bug check (KERNEL_SECURITY_CHECK_FAILURE).</p>

<p>Only system hives are trusted. An <b>RtlQueryRegistryValues</b> call that accesses a system hive does not cause an exception or a bug check if the RTL_QUERY_REGISTRY_DIRECT flag is set and the RTL_QUERY_REGISTRY_TYPECHECK flag is not set. However, as a best practice, the RTL_QUERY_REGISTRY_TYPECHECK flag should always be set if the RTL_QUERY_REGISTRY_DIRECT flag is set.</p>

<p>Similarly, in versions of Windows before Windows 8, as a best practice, an <b>RtlQueryRegistryValues</b> call that sets the RTL_QUERY_REGISTRY_DIRECT flag should additionally set the RTL_QUERY_REGISTRY_TYPECHECK flag. However, failure to follow this recommendation does not cause an exception or a bug check.</p>

<p>The following is a list of system hives:</p>

<p>Support for the RTL_QUERY_REGISTRY_TYPECHECK flag is available through Windows Update for Windows 7, Windows Vista, Windows Server 2003, and Windows XP. For more information about this update, see <a href="http://go.microsoft.com/fwlink/p/?linkid=210698">Vulnerabilities in Windows Kernel Could Allow Elevation of Privilege (2393802)</a>. In versions of these operating systems that do not have this update, the caller can use the RTL_QUERY_REGISTRY_TYPECHECK flag. However, this flag is ignored by the <b>RtlQueryRegistryValues</b> routine.</p>

<p>Starting with Windows Driver Kit (WDK) 8, the RTL_QUERY_REGISTRY_TYPECHECK flag is defined in the Wdm.h header file as follows:</p>

<p>If an entry does not specify the RTL_QUERY_REGISTRY_DIRECT flag, <b>RtlQueryRegistryValues</b> uses the specified <i>QueryRoutine</i> function to report the value name, type, data, and data length, in bytes, to the caller. If the <b>Name</b> member of the entry is <b>NULL</b>, <b>RtlQueryRegistryValues</b> reports every direct subkey of the key. If the key type is REG_MULTI_SZ and the RTL_QUERY_REGISTRY_NOEXPAND flag not is specified, the routine calls <i>QueryRoutine</i> separately for each individual string; otherwise the routine reports it as a single value. If an entry specifies the RTL_QUERY_REGISTRY_DIRECT flag, <b>RtlQueryRegistryValues</b> stores the value of the key in the buffer pointed to by the entry's <b>EntryContext</b> member. The format of the returned data is as follows.</p>

<p>A null-terminated Unicode string (such as REG_SZ, REG_EXPAND_SZ).</p>

<p><b>EntryContext</b> must point to an initialized <a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a> structure. If the <b>Buffer</b> member of <b>UNICODE_STRING</b> is <b>NULL</b>, the routine allocates storage for the string data. Otherwise, it stores the string data in the buffer that <b>Buffer</b> points to.</p>

<p>REG_MULTI_SZ</p>

<p>You must specify the RTL_QUERY_REGISTRY_NOEXPAND flag for this key data type. <b>EntryContext</b> points to an initialized <b>UNICODE_STRING</b> structure. The routine stores the key value as a single string value. Each individual component within the string is terminated by a zero.</p>

<p>If the <b>Buffer</b> member of <b>UNICODE_STRING</b> is <b>NULL</b>, the routine allocates storage for the string data. Otherwise, it stores the string data in the buffer that <b>Buffer</b> points to.</p>

<p>Nonstring data with size, in bytes, &lt;= <b>sizeof</b>(ULONG)</p>

<p>The value is stored in the memory location specified by <b>EntryContext</b>.</p>

<p>Nonstring data with size, in bytes, &gt; <b>sizeof</b>(ULONG)</p>

<p>The buffer pointed to by <b>EntryContext</b> must begin with a signed LONG value. The magnitude of the value must specify the size, in bytes, of the buffer. If the sign of the value is negative, <b>RtlQueryRegistryValues</b> will only store the data of the key value. Otherwise, it will use the first ULONG in the buffer to record the value length, in bytes, the second ULONG to record the value type, and the rest of the buffer to store the value data.</p>

<p>If an error occurs at any stage of processing of the query table, <b>RtlQueryRegistryValues</b> stops processing the table and returns the error status.</p>

<p>See <a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a> for a description of the possible REG_<i>XXX</i> values.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.queryroutine">QueryRoutine</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlzeromemory.md">RtlZeroMemory</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwenumeratevaluekey.md">ZwEnumerateValueKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlQueryRegistryValues routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
