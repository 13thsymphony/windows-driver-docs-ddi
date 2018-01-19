---
UID : NF:wdm.ExCreateCallback
title : ExCreateCallback function
author : windows-driver-content
description : The ExCreateCallback routine either creates a new callback object or opens an existing callback object on behalf of the caller.
old-location : kernel\excreatecallback.htm
old-project : kernel
ms.assetid : a8532a6d-2b7f-4ed6-a2e4-6157d5e842ff
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ExCreateCallback
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
req.alt-api : ExCreateCallback
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : IrqlExPassive, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : <= APC_LEVEL
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ExCreateCallback function
The <b>ExCreateCallback</b> routine either creates a new callback object or opens an existing callback object on behalf of the caller.

## Syntax

````
NTSTATUS ExCreateCallback(
  _Out_ PCALLBACK_OBJECT   *CallbackObject,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes,
  _In_  BOOLEAN            Create,
  _In_  BOOLEAN            AllowMultipleCallbacks
);
````

## Parameters

`CallbackObject`

A pointer to a location that receives a pointer to a callback object, which is an opaque, system structure. If the <b>ExCreateCallback</b> call succeeds, the routine writes the address of the newly created or opened callback object to this location. The callback object pointer obtained from this routine can be supplied as a parameter to the <a href="..\wdm\nf-wdm-exregistercallback.md">ExRegisterCallback</a> or <a href="..\wdm\nf-wdm-exnotifycallback.md">ExNotifyCallback</a> routine.

`ObjectAttributes`

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that contains the callback object's attributes. This structure was previously initialized by the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> routine.

`Create`

Whether to create a callback object. Set to <b>TRUE</b> to create a new callback object if the requested object cannot be opened. Otherwise, set to <b>FALSE</b>.

`AllowMultipleCallbacks`

Whether a newly created callback object should allow multiple registered callback routines. Set to <b>TRUE</b> to allow multiple registered callback routines. Otherwise, set to <b>FALSE</b>. This parameter is ignored when <i>Create</i> is <b>FALSE</b> or when opening an existing object.


## Return Value

<b>ExCreateCallback</b> returns STATUS_SUCCESS if a callback object was opened or created. Otherwise, it returns an NTSTATUS error code to indicate the nature of the failure.

## Remarks

A driver calls <b>ExCreateCallback</b> to create a new callback object or to open an existing callback object. After the object has been created or opened, other components can call the <a href="..\wdm\nf-wdm-exregistercallback.md">ExRegisterCallback</a> routine to register callback routines with the callback object.

Before calling <b>ExCreateCallback</b>, the driver must call <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> to initialize the <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure for the callback object. Unnamed callback objects are not permitted. The caller must specify a name for the object; otherwise, the call fails with STATUS_UNSUCCESSFUL. The caller should specify the OBJ_PERMANENT attribute in the callback object to prevent the object from being deleted before it can be registered with the object manager. The caller should also specify any other attributes, such as OBJ_CASE_INSENSITIVE, that might be needed.

When all operations have been completed with the callback object, the driver must delete the object to prevent a memory leak. For information about deleting an object  that was created with the OBJ_PERMANENT object attribute, see <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>.

The following table shows the callback objects that the operating system creates for use by drivers.

\Callback\SetSystemTime

The operating system calls any callback routines registered for this object whenever the system time changes.

\Callback\PowerState

The operating system calls any callback routines registered for this object  whenever certain system power characteristics change. When a driver registers for callback notification (by calling <b>ExRegisterCallback</b>), it can specify the changes for which it should be notified.

For more information about callback objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540718">Callback Objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** | IrqlExPassive, HwStorPortProhibitedDDIs |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-exregistercallback.md">ExRegisterCallback</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exnotifycallback.md">ExNotifyCallback</a>
</dt>
<dt>
<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExCreateCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>