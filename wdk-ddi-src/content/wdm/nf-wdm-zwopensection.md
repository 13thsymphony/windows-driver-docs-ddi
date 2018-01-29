---
UID : NF:wdm.ZwOpenSection
title : ZwOpenSection function
author : windows-driver-content
description : The ZwOpenSection routine opens a handle for an existing section object.
old-location : kernel\zwopensection.htm
old-project : kernel
ms.assetid : c4373f7b-cc88-45da-a140-ead1c6891c11
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.zwopensection, NtOpenSection, wdm/ZwOpenSection, ZwOpenSection, ZwOpenSection routine [Kernel-Mode Driver Architecture], k111_51851f81-8825-499b-9e7e-36faa8f53b23.xml, wdm/NtOpenSection
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


# ZwOpenSection function
The <b>ZwOpenSection</b> routine opens a handle for an existing <a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">section object</a>.

## Syntax

````
NTSTATUS ZwOpenSection(
  _Out_ PHANDLE            SectionHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes
);
````

## Parameters

`SectionHandle`

Pointer to a HANDLE variable that receives a handle to the section object.

`DesiredAccess`

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that determines the requested access to the object. For more information, see the <i>DesiredAccess</i> parameter of <a href="..\wdm\nf-wdm-zwcreatesection.md">ZwCreateSection</a>.

`ObjectAttributes`

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.


## Return Value

<b>ZwOpenSection</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible return values include:

## Remarks

If the section does not exist or the system did not grant the requested access, the operation fails.

Once the handle pointed to by <i>SectionHandle</i> is no longer in use, the driver must call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.
<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtOpenSection</b>" instead of "<b>ZwOpenSection</b>".</div><div> </div>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="..\wdm\nf-wdm-zwunmapviewofsection.md">ZwUnmapViewOfSection</a>

<a href="..\wdm\nf-wdm-zwcreatesection.md">ZwCreateSection</a>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>

<a href="..\wdm\nf-wdm-zwmapviewofsection.md">ZwMapViewOfSection</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenSection routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>