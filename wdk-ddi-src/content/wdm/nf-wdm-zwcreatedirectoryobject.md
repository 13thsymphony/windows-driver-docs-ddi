---
UID : NF:wdm.ZwCreateDirectoryObject
title : ZwCreateDirectoryObject function
author : windows-driver-content
description : The ZwCreateDirectoryObject routine creates or opens an object-directory object.
old-location : kernel\zwcreatedirectoryobject.htm
old-project : kernel
ms.assetid : 45e4a08d-9615-410a-8f78-a8157802813f
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : k111_b1b0f371-6699-42f6-b86d-a0fb57983d9f.xml, NtCreateDirectoryObject, wdm/NtCreateDirectoryObject, ZwCreateDirectoryObject routine [Kernel-Mode Driver Architecture], ZwCreateDirectoryObject, wdm/ZwCreateDirectoryObject, kernel.zwcreatedirectoryobject
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
req.ddi-compliance : PowerIrpDDis, HwStorPortProhibitedDDIs
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


# ZwCreateDirectoryObject function
The <b>ZwCreateDirectoryObject</b> routine creates or opens an object-directory object.

## Syntax

````
NTSTATUS ZwCreateDirectoryObject(
  _Out_ PHANDLE            DirectoryHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes
);
````

## Parameters

`DirectoryHandle`

Pointer to a HANDLE variable that receives a handle to the object directory.

`DesiredAccess`

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

`ObjectAttributes`

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that contains the object's attributes, which you must have already initialized by calling <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>.


## Return Value

<b>ZwCreateDirectoryObject</b> returns an NTSTATUS value. Possible return values include:

## Remarks

Once the handle pointed to by <i>DirectoryHandle</i> is no longer in use, the driver must call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

The system uses object directories to organize other types of objects, such as device objects. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557755">Object Directories</a>.

Note that the system does <u>not</u> use object directory objects to represent file-system directories, which are represented instead as file objects.
<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtCreateDirectoryObject</b>" instead of "<b>ZwCreateDirectoryObject</b>". </div><div> </div>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCreateDirectoryObject routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>