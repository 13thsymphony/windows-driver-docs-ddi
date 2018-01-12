---
UID: NF:wdm.RtlVerifyVersionInfo
title: RtlVerifyVersionInfo function
author: windows-driver-content
description: The RtlVerifyVersionInfo routine compares a specified set of operating system version requirements to the corresponding attributes of the currently running version of the operating system.
old-location: kernel\rtlverifyversioninfo.htm
old-project: kernel
ms.assetid: 7c0ca9a0-dfa4-44ab-8d3a-ab43f72c806f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlVerifyVersionInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlVerifyVersionInfo
req.alt-loc: NtosKrnl.exe,Ntdll.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlVerifyVersionInfo function



## -description
The <b>RtlVerifyVersionInfo</b> routine compares a specified set of operating system version requirements to the corresponding attributes of the currently running version of the operating system.



## -syntax

````
NTSTATUS RtlVerifyVersionInfo(
  _In_ PRTL_OSVERSIONINFOEXW VersionInfo,
  _In_ ULONG                 TypeMask,
  _In_ ULONGLONG             ConditionMask
);
````


## -parameters

### -param VersionInfo [in]

Pointer to an <a href="..\wdm\ns-wdm-_osversioninfoexw.md">RTL_OSVERSIONINFOEXW</a> structure that specifies the operating system version requirements to compare to the corresponding attributes of the currently running version of the operating system. 


### -param TypeMask [in]

Specifies which members of <i>VersionInfo</i> to compare with the corresponding attributes of the currently running version of the operating system. <i>TypeMask</i> is set to a logical OR of one or more of the following values.
                        

<table>
<tr>
<th>Value</th>
<th>Corresponding member</th>
</tr>
<tr>
<td>
VER_BUILDNUMBER

</td>
<td>
<b>dwBuildNumber</b>

</td>
</tr>
<tr>
<td>
VER_MAJORVERSION

</td>
<td>
<b>dwMajorVersion</b>

</td>
</tr>
<tr>
<td>
VER_MINORVERSION

</td>
<td>
<b>dwMinorVersion</b>

</td>
</tr>
<tr>
<td>
VER_PLATFORMID

</td>
<td>
<b>dwPlatformId</b>

</td>
</tr>
<tr>
<td>
VER_SERVICEPACKMAJOR

</td>
<td>
<b>wServicePackMajor</b>

</td>
</tr>
<tr>
<td>
VER_SERVICEPACKMINOR

</td>
<td>
<b>wServicePackMinor</b>

</td>
</tr>
<tr>
<td>
VER_SUITENAME

</td>
<td>
<b>wSuiteMask</b>

</td>
</tr>
<tr>
<td>
VER_PRODUCT_TYPE

</td>
<td>
<b>wProductType</b>

</td>
</tr>
</table>
 


### -param ConditionMask [in]

Specifies how to compare each <b>VersionInfo</b> member. To set the value of <i>ConditionMask</i>, a caller should use the <b>VER_SET_CONDITION</b> macro:
						  

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VER_SET_CONDITION (
        IN OUT  ULONGLONG  ConditionMask,
        IN ULONG  TypeBitMask,
        IN UCHAR  ComparisonType
        );</pre>
</td>
</tr>
</table></span></div>
The value of <i>ConditionMask</i> is created in the following way:

<ul>
<li>
Initialize the value of <i>ConditionMask</i> to zero. 

</li>
<li>
Call <b>VER_SET_CONDITION</b> once for each <i>VersionInfo</i> member specified by <i>TypeMask</i>.

</li>
<li>
Set the <i>TypeBitMask</i> and <i>ComparisonType</i> parameters for each call to <b>VER_SET_CONDITION</b> as follows:

</li>
</ul>



### -param TypeBitMask

Indicates the <i>VersionInfo</i> member for which the comparison type is set. <i>TypeBitMask</i> can be one of the following values.
        

<table>
<tr>
<th>Value</th>
<th>Corresponding member</th>
</tr>
<tr>
<td>
VER_BUILDNUMBER

</td>
<td>
<b>dwBuildNumber</b>

</td>
</tr>
<tr>
<td>
VER_MAJORVERSION

</td>
<td>
<b>dwMajorVersion</b>

</td>
</tr>
<tr>
<td>
VER_MINORVERSION

</td>
<td>
<b>dwMinorVersion</b>

</td>
</tr>
<tr>
<td>
VER_PLATFORMID

</td>
<td>
<b>dwPlatformId</b>

</td>
</tr>
<tr>
<td>
VER_SERVICEPACKMAJOR

</td>
<td>
<b>wServicePackMajor</b>

</td>
</tr>
<tr>
<td>
VER_SERVICEPACKMINOR

</td>
<td>
<b>wServicePackMinor</b>

</td>
</tr>
<tr>
<td>
VER_SUITENAME

</td>
<td>
<b>wSuiteMask</b>

</td>
</tr>
<tr>
<td>
VER_PRODUCT_TYPE

</td>
<td>
<b>wProductType</b>

</td>
</tr>
</table>
 


### -param ComparisonType

Specifies the comparison type that <b>RtlVerifyVersionInfo</b> uses to compare the <b>VersionInfo</b> member specified by <i>TypeBitMask</i> with the corresponding attribute of the currently running operating system.
        

For all values of <i>TypeBitMask</i> other than VER_SUITENAME, <i>ComparisonType</i> is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VER_EQUAL

</td>
<td>
The current value must be equal to the specified value.

</td>
</tr>
<tr>
<td>
VER_GREATER

</td>
<td>
The current value must be greater than the specified value.

</td>
</tr>
<tr>
<td>
VER_GREATER_EQUAL

</td>
<td>
The current value must be greater than or equal to the specified value.

</td>
</tr>
<tr>
<td>
VER_LESS

</td>
<td>
The current value must be less than the specified value.

</td>
</tr>
<tr>
<td>
VER_LESS_EQUAL

</td>
<td>
The current value must be less than or equal to the specified value.

</td>
</tr>
</table>
 

If <i>TypeBitMask</i> is set to VER_SUITENAME, <i>ComparisonType</i> is set to of one the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VER_AND

</td>
<td>
All product suites specified in the <b>wSuiteMask</b> member must be present in the current system.

</td>
</tr>
<tr>
<td>
VER_OR

</td>
<td>
At least one of the specified product suites must be present in the current system.

</td>
</tr>
</table>
 

</dd>
</dl>

## -returns
<b>RtlVerifyVersionInfo</b> returns one of the following status values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The specified version matches the currently running version of the operating system.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The input parameters are not valid.
<dl>
<dt><b>STATUS_REVISION_MISMATCH</b></dt>
</dl>The specified version does not match the currently running version of the operating system.

 


## -remarks
<b>RtlVerifyVersionInfo</b> enables a driver to easily verify the presence of a required set of operating system attributes. <b>RtlVerifyVersionInfo</b> is the kernel-mode equivalent of the user-mode <b>VerifyVersionInfo</b> function in the Windows SDK. See the example in the Windows SDK that shows how to verify the system version.

Typically, <b>RtlVerifyVersionInfo</b> returns STATUS_SUCCESS only if all comparisons succeed. However, the major version, minor version, and service pack version are tested in a sequential manner in the following way:

If the major version exceeds the minimum required, then the minor version and service pack version are not tested. For example, if the current major version is 6.0, a test for a system greater than or equal to version 5.1 service pack 1 succeeds. The minor version and service pack version are not tested.

If the minor version exceeds the minimum required, then the service pack version is not tested. For example, if the current major version is 5.2, a test for a system version greater than or equal to version 5.1 service pack 1 succeeds. The service pack version is not tested.

If the major service pack version exceeds the minimum required, then the minor service pack version is not tested.

To verify a range of system versions, a driver can call <b>RtlVerifyVersionInfo</b> twice, once to verify a lower bound on the system version and once to verify an upper bound on the system version.


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
Version

</th>
<td width="70%">
Available in Windows 2000 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe (kernel mode); </dt>
<dt>Ntdll.dll (user mode)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlgetversion.md">RtlGetVersion</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_osversioninfow.md">RTL_OSVERSIONINFOW</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_osversioninfoexw.md">RTL_OSVERSIONINFOEXW</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlVerifyVersionInfo routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

