---
UID: NF.wdm.ZwQueryFullAttributesFile
title: ZwQueryFullAttributesFile function
author: windows-driver-content
description: The ZwQueryFullAttributesFile routine supplies network open information for the specified file.
old-location: kernel\zwqueryfullattributesfile.htm
old-project: kernel
ms.assetid: 896ea6aa-54e8-4109-8597-58d8d2cd75ce
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: ZwQueryFullAttributesFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwQueryFullAttributesFile,NtQueryFullAttributesFile
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# ZwQueryFullAttributesFile function



## -description
The <b>ZwQueryFullAttributesFile</b> routine supplies network open information for the specified file.


## -syntax

````
NTSTATUS ZwQueryFullAttributesFile(
  _In_  POBJECT_ATTRIBUTES             ObjectAttributes,
  _Out_ PFILE_NETWORK_OPEN_INFORMATION FileInformation
);
````


## -parameters

### -param ObjectAttributes [in]

A pointer to an <a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a> structure that supplies the attributes to be used for the file object. 

### -param FileInformation [out]

A pointer to a <a href="kernel.file_network_open_information">FILE_NETWORK_OPEN_INFORMATION</a> structure that receives the returned file attributes information. 

## -returns
<b>ZwQueryFullAttributesFile</b> returns STATUS_SUCCESS on success, or the appropriate error status.

## -remarks
Callers of <b>ZwQueryFullAttributesFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<b>NtQueryFullAttributesFile</b> and <b>ZwQueryFullAttributesFile</b> are two versions of the same Windows Native System Services routine. The <b>NtQueryFullAttributesFile</b> routine in the Windows kernel is not directly accessible to kernel-mode drivers. However, kernel-mode drivers can access this routine indirectly by calling the <b>ZwQueryFullAttributesFile</b> routine. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

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
Available starting with Windows XP.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL (see Remarks section)
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.file_network_open_information">FILE_NETWORK_OPEN_INFORMATION</a>
</dt>
<dt>
<a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryFullAttributesFile routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
