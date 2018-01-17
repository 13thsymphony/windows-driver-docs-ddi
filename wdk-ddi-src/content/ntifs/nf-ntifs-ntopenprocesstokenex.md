---
UID: NF:ntifs.NtOpenProcessTokenEx
title: NtOpenProcessTokenEx function
author: windows-driver-content
description: The ZwOpenProcessTokenEx routine opens the access token associated with a process.
old-location: kernel\zwopenprocesstokenex.htm
old-project: kernel
ms.assetid: 2ea6f764-b884-4764-a2ff-19d0170f9b31
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: NtOpenProcessTokenEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwOpenProcessTokenEx,NtOpenProcessTokenEx
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
req.irql: PASSIVE_LEVEL
req.typenames: TOKEN_TYPE
---

# NtOpenProcessTokenEx function



## -description
The <b>ZwOpenProcessTokenEx</b> routine opens the access token associated with a process. 



## -syntax

````
NTSTATUS ZwOpenProcessTokenEx(
  _In_  HANDLE      ProcessHandle,
  _In_  ACCESS_MASK DesiredAccess,
  _In_  ULONG       HandleAttributes,
  _Out_ PHANDLE     TokenHandle
);
````


## -parameters

### -param ProcessHandle [in]

Handle to the process whose access token is to be opened. The handle must have PROCESS_QUERY_INFORMATION access. Use the <b>NtCurrentProcess</b> macro, defined in Ntddk.h, to specify the current process. 


### -param DesiredAccess [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> structure specifying the requested types of access to the access token. These requested access types are compared with the token's discretionary access-control list (<a href="..\wdm\ns-wdm-_acl.md">DACL</a>) to determine which accesses are granted or denied.


### -param HandleAttributes [in]

Attributes for the access token handle. Only OBJ_KERNEL_HANDLE is currently supported. If the caller is not running in the system process context, it must specify OBJ_KERNEL_HANDLE for this parameter. 


### -param TokenHandle [out]

Pointer to a caller-allocated variable that receives a handle to the newly opened access token. 


## -returns
<b>ZwOpenProcessTokenEx</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following: 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><i>ProcessHandle</i> did not have PROCESS_QUERY_INFORMATION access. 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A new token handle could not be allocated. 
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl><i>ProcessHandle</i> was not a valid handle. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The specified <i>HandleAttributes</i> did not include OBJ_KERNEL_HANDLE. 
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl><i>ProcessHandle</i> was not a process handle. 
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>The caller does not have the privilege (SeSecurityPrivilege) necessary to create a token handle with the access specified in the <i>DesiredAccess</i> parameter. 
<dl>
<dt><b>STATUS_QUOTA_EXCEEDED</b></dt>
</dl>The process's memory quota is not sufficient to allocate the token handle. 
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The token handle could not be created. 

 


## -remarks
<b>ZwOpenProcessTokenEx</b> opens the access token associated with a process and returns a handle for that token. 

Any handle obtained by calling <b>ZwOpenProcessTokenEx</b> must eventually be released by calling <b>ZwClose</b>. 

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the <i>HandleAttributes</i> parameter of <b>ZwOpenProcessTokenEx</b>. This restricts the use of the handle returned by <b>ZwOpenProcessTokenEx</b> to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running. 

For more information about security and access control, see the documentation on these topics in the Windows SDK. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_acl.md">ACL</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-psdereferenceprimarytoken.md">PsDereferencePrimaryToken</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwopenthreadtokenex.md">ZwOpenThreadTokenEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenProcessTokenEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

