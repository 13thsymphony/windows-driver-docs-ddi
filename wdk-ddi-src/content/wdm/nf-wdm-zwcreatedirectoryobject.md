---
UID: NF.wdm.ZwCreateDirectoryObject
title: ZwCreateDirectoryObject function
author: windows-driver-content
description: The ZwCreateDirectoryObject routine creates or opens an object-directory object.
old-location: kernel\zwcreatedirectoryobject.htm
old-project: kernel
ms.assetid: 45e4a08d-9615-410a-8f78-a8157802813f
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: ZwCreateDirectoryObject
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
req.alt-api: ZwCreateDirectoryObject,NtCreateDirectoryObject
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
req.product: Windows 10 or later.
---

# ZwCreateDirectoryObject function



## -description
The <b>ZwCreateDirectoryObject</b> routine creates or opens an object-directory object.



## -syntax

````
NTSTATUS ZwCreateDirectoryObject(
  _Out_ PHANDLE            DirectoryHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes
);
````


## -parameters

### -param DirectoryHandle [out]

Pointer to a HANDLE variable that receives a handle to the object directory.


### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that determines the requested access to the object. In addition to the access rights that are defined for all types of objects (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>), the caller can specify one or more of the following access rights, which are specific to object directories:

<table>
<tr>
<th>ACCESS_MASK flag</th>
<th>Type of access</th>
</tr>
<tr>
<td>
DIRECTORY_QUERY

</td>
<td>
Query

</td>
</tr>
<tr>
<td>
DIRECTORY_TRAVERSE

</td>
<td>
Name lookup

</td>
</tr>
<tr>
<td>
DIRECTORY_CREATE_OBJECT

</td>
<td>
Name creation

</td>
</tr>
<tr>
<td>
DIRECTORY_CREATE_SUBDIRECTORY

</td>
<td>
Subdirectory creation

</td>
</tr>
<tr>
<td>
DIRECTORY_ALL_ACCESS

</td>
<td>
All of the preceding types

</td>
</tr>
</table>
 


### -param ObjectAttributes [in]

Pointer to an <a href="kernel.object_attributes">OBJECT_ATTRIBUTES</a> structure that contains the object's attributes, which you must have already initialized by calling <a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a>. 


## -returns
<b>ZwCreateDirectoryObject</b> returns an NTSTATUS value. Possible return values include:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
<dt><b>STATUS_DATATYPE_MISALIGNMENT</b></dt>
</dl>

## -remarks
Once the handle pointed to by <i>DirectoryHandle</i> is no longer in use, the driver must call <a href="kernel.zwclose">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

The system uses object directories to organize other types of objects, such as device objects. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557755">Object Directories</a>.

Note that the system does <u>not</u> use object directory objects to represent file-system directories, which are represented instead as file objects.

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
Available starting with Windows 2000.

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
PASSIVE_LEVEL

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="kernel.initializeobjectattributes">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCreateDirectoryObject routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

