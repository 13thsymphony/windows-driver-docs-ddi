---
UID: NS.WDM._OB_POST_OPERATION_INFORMATION
title: _OB_POST_OPERATION_INFORMATION
author: windows-driver-content
description: The OB_POST_OPERATION_INFORMATION structure provides information about a process or thread handle operation to an ObjectPostCallback routine.
old-location: kernel\ob_post_operation_information.htm
old-project: kernel
ms.assetid: fc52e06d-c826-43c2-ac61-4f56fd808d43
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _OB_POST_OPERATION_INFORMATION, *POB_POST_OPERATION_INFORMATION, OB_POST_OPERATION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Server 2008 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OB_POST_OPERATION_INFORMATION
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _OB_POST_OPERATION_INFORMATION structure



## -description
The <b>OB_POST_OPERATION_INFORMATION</b> structure provides information about a process or thread handle operation to an <a href="kernel.objectpostcallback">ObjectPostCallback</a> routine.


## -syntax

````
typedef struct _OB_POST_OPERATION_INFORMATION {
  OB_OPERATION                  Operation;
  union {
    ULONG  Flags;
    struct {
      ULONG KernelHandle  :1;
      ULONG Reserved  :31;
    };
  };
  PVOID                         Object;
  POBJECT_TYPE                  ObjectType;
  PVOID                         CallContext;
  NTSTATUS                      ReturnStatus;
  POB_POST_OPERATION_PARAMETERS Parameters;
} OB_POST_OPERATION_INFORMATION, *POB_POST_OPERATION_INFORMATION;
````


## -struct-fields

### -field Operation

The type of handle operation. This member might be one of the following values:


### -field OB_OPERATION_HANDLE_CREATE

A new handle to a process or thread was created. Use <b>Parameters-&gt;CreateHandleInformation</b> for create-specific information.

### -field OB_OPERATION_HANDLE_DUPLICATE

A process or thread handle was duplicated. Use <b>Parameters-&gt;DuplicateHandleInformation</b> for duplicate-specific information.
</dd>
</dl>

### -field Flags

Reserved. Use the <b>KernelHandle</b> member instead. 

### -field KernelHandle

A ULONG value that specifies whether the handle is a kernel handle. If this value is <b>TRUE</b>, the handle is a kernel handle. Otherwise, the handle is not a kernel handle.

### -field Reserved

Reserved for system use.

### -field Object

A pointer to the process or thread object that is the target of the handle operation.

### -field ObjectType

A pointer to the object type of the object. This type can be <b>PsProcessType</b> for a process or <b>PsThreadType</b> for a thread. 

### -field CallContext

A pointer to driver-specific context information for the operation. This value is the value that the <i>OperationInformation</i>-&gt;<b>CallContext</b> member specifies to the <a href="kernel.objectprecallback">ObjectPreCallback</a> routine. 

### -field ReturnStatus

The NTSTATUS value for the handle operation.

### -field Parameters

A pointer to an <a href="kernel.ob_post_operation_parameters">OB_POST_OPERATION_PARAMETERS</a> union that contains operation-specific information. The <b>Operation</b> member determines which member of the union is valid. The pointer is valid only when <b>ReturnStatus</b> is a success code.

## -remarks
Unlike the <a href="kernel.ob_pre_operation_information">OB_PRE_OPERATION_INFORMATION</a> structure, the members of the <b>OB_POST_OPERATION_INFORMATION</b> structure are purely informational; you cannot modify them.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Server 2008 and later versions of the Windows operating system.
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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ob_pre_operation_information">OB_PRE_OPERATION_INFORMATION</a>
</dt>
<dt>
<a href="kernel.objectpostcallback">ObjectPostCallback</a>
</dt>
<dt>
<a href="kernel.objectprecallback">ObjectPreCallback</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20OB_POST_OPERATION_INFORMATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
