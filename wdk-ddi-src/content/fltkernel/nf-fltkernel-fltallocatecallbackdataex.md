---
UID: NF.fltkernel.FltAllocateCallbackDataEx
title: FltAllocateCallbackDataEx function
author: windows-driver-content
description: The FltAllocateCallbackDataEx routine allocates a callback data structure and can preallocate memory for additional structures that a minifilter driver can use to initiate an I/O request.
old-location: ifsk\fltallocatecallbackdataex.htm
old-project: ifsk
ms.assetid: f03851a4-e1e9-4fee-b264-c2f91c6e8180
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltAllocateCallbackDataEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltAllocateCallbackDataEx
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
---

# FltAllocateCallbackDataEx function



## -description
The <b>FltAllocateCallbackDataEx</b> routine allocates a callback data structure and can preallocate memory for additional structures that a minifilter driver can use to initiate an I/O request.



## -syntax

````
NTSTATUS FltAllocateCallbackDataEx(
  _In_     PFLT_INSTANCE                    Instance,
  _In_opt_ PFILE_OBJECT                     FileObject,
  _In_     FLT_ALLOCATE_CALLBACK_DATA_FLAGS Flags,
  _Out_    PFLT_CALLBACK_DATA               *RetNewCallbackData
);
````


## -parameters

### -param Instance [in]

An opaque instance pointer to the minifilter driver instance that is initiating the I/O operation. This parameter is required and cannot be <b>NULL</b>.


### -param FileObject [in, optional]

A pointer to a file object to be used in the I/O operation. This parameter is optional and can be <b>NULL</b>.


### -param Flags [in]

A value of zero or the following flag:

        FLT_ALLOCATE_CALLBACK_DATA_PREALLOCATE_ALL_MEMORY

If this flag is set, the routine preallocates all the memory needed by the filter manager for additional structures to be used in an I/O request.


### -param RetNewCallbackData [out]

A pointer to a caller-allocated variable that receives the address of the newly allocated callback data (<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>) structure.


## -returns
The <b>FltAllocateCallbackDataEx</b> routine returns STATUS_SUCCESS on success or STATUS_INSUFFICIENT_RESOURCES if the routine encountered a pool allocation failure when attempting to allocate the callback data structure or if the FLT_ALLOCATE_CALLBACK_DATA_PREALLOCATE_ALL_MEMORY flag is set and additional memory could not be allocated.


## -remarks
If the FLT_ALLOCATE_CALLBACK_DATA_PREALLOCATE_ALL_MEMORY flag is set, the routine allocates all the memory needed for additional filter manager structures to be used in a subsequent I/O request. Using this flag enables a minifilter to preallocate one or more callback data structures to be used for issuing I/O requests under low memory conditions or in situations where recovering from a memory allocation failure might be complicated. 

Set <i>FileObject</i> to <b>NULL</b> if this is a CREATE operation.


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
Available in Windows 7 and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include FltKernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltallocatecallbackdata">FltAllocateCallbackData</a>
</dt>
<dt>
<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAllocateCallbackDataEx routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

