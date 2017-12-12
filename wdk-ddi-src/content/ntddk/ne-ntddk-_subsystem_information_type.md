---
UID: NE.ntddk._SUBSYSTEM_INFORMATION_TYPE
title: _SUBSYSTEM_INFORMATION_TYPE
author: windows-driver-content
description: Indicates the type of subsystem for a process or thread. This enumeration is used in NtQueryInformationProcess and NtQueryInformationThread calls.
old-location: kernel\subsystem_information_type.htm
old-project: kernel
ms.assetid: B1E334BF-AAB3-410D-8D10-A750E8459E42
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _SUBSYSTEM_INFORMATION_TYPE, *PSUBSYSTEM_INFORMATION_TYPE, SUBSYSTEM_INFORMATION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SUBSYSTEM_INFORMATION_TYPE
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _SUBSYSTEM_INFORMATION_TYPE enumeration



## -description
Indicates the type of subsystem for a process or thread. This enumeration is used in <a href="base.ntqueryinformationprocess">NtQueryInformationProcess</a>  and <a href="base.ntqueryinformationthread">NtQueryInformationThread</a> calls. 



## -syntax

````
typedef enum _SUBSYSTEM_INFORMATION_TYPE { 
  SubsystemInformationTypeWin32  = 0,
  SubsystemInformationTypeWSL    = 1,
  MaxSubsystemInformationType
} SUBSYSTEM_INFORMATION_TYPE;
````


## -enum-fields

### -field SubsystemInformationTypeWin32

The subsystem type for the process or thread is Win32.


### -field SubsystemInformationTypeWSL

The subsystem type for the process or thread is Windows Subsystem for Linux (WSL). For this process, these members of  the <a href="kernel.ps_create_notify_info">PS_CREATE_NOTIFY_INFO</a> structure are set as follows:

<ul>
<li>The <b>FileObject</b> member is the NTFS file object from LxFs or DriveFs, the file system that is used for interoperability with Windows. </li>
<li>The <b>ImageFileName</b> member is the Linux path of the image file. </li>
<li>The <b>CommandLine</b> member is the Linux NULL-separated command line. </li>
</ul>
 The preceding member values may be NULL.


### -field MaxSubsystemInformationType

Reserved.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="base.ntqueryinformationthread">NtQueryInformationThread</a>
</dt>
<dt>
<a href="base.ntqueryinformationprocess">NtQueryInformationProcess</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SUBSYSTEM_INFORMATION_TYPE enumeration%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

