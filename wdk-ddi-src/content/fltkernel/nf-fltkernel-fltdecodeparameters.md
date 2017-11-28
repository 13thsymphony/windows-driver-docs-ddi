---
UID: NF.fltkernel.FltDecodeParameters
title: FltDecodeParameters
author: windows-driver-content
description: FltDecodeParameters returns pointers to the memory descriptor list (MDL) address, buffer pointer, buffer length, and desired access parameters for an I/O operation.
old-location: ifsk\fltdecodeparameters.htm
old-project: ifsk
ms.assetid: c0569a55-7bc0-4c98-80b9-c332c313ca5b
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: FltDecodeParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltDecodeParameters
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
req.irql: Any level
req.iface: 
---

# FltDecodeParameters function



## -description
<p><b>FltDecodeParameters</b> returns pointers to the memory descriptor list (MDL) address, buffer pointer, buffer length, and desired access parameters for an I/O operation. This saves minifilter drivers from having a switch statement to find the position of these parameters in helper routines that access the MDL address, buffer pointer, buffer length, and desired access for multiple operation types. </p>


## -syntax

````
NTSTATUS FltDecodeParameters(
  _In_      PFLT_CALLBACK_DATA CallbackData,
  _Out_     PMDL               **MdlAddressPointer,
  _Out_     PVOID              **Buffer,
  _Out_     PULONG             *Length,
  _Out_opt_ LOCK_OPERATION     *DesiredAccess
);
````


## -parameters
<dl>

### -param <i>CallbackData</i> [in]

<dd>
<p>Pointer to the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for the I/O operation. </p>
</dd>

### -param <i>MdlAddressPointer</i> [out]

<dd>
<p>Pointer to a caller-supplied variable that receives a pointer to the <b>MdlAddress</b> (or <b>OutputMdlAddress</b>) member of the callback data parameter (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544673">FLT_PARAMETERS</a>) structure (note that this member is itself a pointer). This parameter is optional and can be <b>NULL</b>. If the I/O operation does not have an MDL field, this parameter receives <b>NULL</b>. </p>
</dd>

### -param <i>Buffer</i> [out]

<dd>
<p>Pointer to a caller-supplied variable that receives a pointer to the appropriate buffer member (depending on the major function code) in the callback data parameter structure (note that this member is itself a pointer). </p>
</dd>

### -param <i>Length</i> [out]

<dd>
<p>Pointer to a caller-supplied variable that receives a pointer to the buffer length member in the callback data parameter structure. If the operation does not have a length field, this parameter receives <b>NULL</b>. </p>
</dd>

### -param <i>DesiredAccess</i> [out, optional]

<dd>
<p>Pointer to a caller-supplied variable that receives the type of access that is appropriate for this type of I/O operation, one of <code>IoReadAccess</code>, <code>IoWriteAccess</code>, or <code>IoModifyAccess</code>. <code>IoReadAccess</code> means that the minifilter driver can examine the contents of the buffer but cannot change the contents in place. <code>IoWriteAccess</code> and <code>IoModifyAccess</code>, which are equivalent, mean that the minifilter driver has read and write access to the buffer. </p>
</dd>
</dl>

## -returns
<p><b>FltDecodeParameters</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: </p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure represents an I/O operation that does not have any buffer parameters. This is an error code. </p>

<p> </p>

## -remarks
<p><b>FltDecodeParameters</b> returns pointers to the parameters for an I/O operation, rather than the parameter values, so that the caller can modify the values of the parameters if desired. </p>

<p><b>FltDecodeParameters</b> can be used for fast I/O operations as well as IRP-based operations. It is not meaningful for file system filter (FSFilter) callback operations, because those operations do not have buffer parameters. </p>

<p>IOCTL and FSCTL operations can have one or two buffers, depending on the buffering method used. In cases where the operation has two buffers (and two length fields), <b>FltDecodeParameters</b> returns the <b>OutputBuffer</b>, <b>OutputBufferLength</b>, and/or <b>OutputMdlAddress</b> fields as appropriate. </p>

<p>Not all of the four parameters are returned for every I/O operation. For example, for an IRP_MJ_READ request, <b>FltDecodeParameters</b> sets the output parameters as follows. </p>

<p><i>MdlAddressPointer</i></p>

<p>&amp;(CallbackData-&gt;Iopb-&gt;Parameters.Read.MdlAddress)</p>

<p><i>Buffer</i></p>

<p>&amp;(CallbackData-&gt;Iopb-&gt;Parameters.Read.ReadBuffer)</p>

<p><i>Length</i></p>

<p>&amp;(CallbackData-&gt;Iopb-&gt;Parameters.Read.Length)</p>

<p><i>DesiredAccess</i></p>

<p>IoWriteAccess</p>

<p> </p>

<p><b>FltDecodeParameters</b> returns pointers to the parameters for an I/O operation, rather than the parameter values, so that the caller can modify the values of the parameters if desired. </p>

<p><b>FltDecodeParameters</b> can be used for fast I/O operations as well as IRP-based operations. It is not meaningful for file system filter (FSFilter) callback operations, because those operations do not have buffer parameters. </p>

<p>IOCTL and FSCTL operations can have one or two buffers, depending on the buffering method used. In cases where the operation has two buffers (and two length fields), <b>FltDecodeParameters</b> returns the <b>OutputBuffer</b>, <b>OutputBufferLength</b>, and/or <b>OutputMdlAddress</b> fields as appropriate. </p>

<p>Not all of the four parameters are returned for every I/O operation. For example, for an IRP_MJ_READ request, <b>FltDecodeParameters</b> sets the output parameters as follows. </p>

<p><i>MdlAddressPointer</i></p>

<p>&amp;(CallbackData-&gt;Iopb-&gt;Parameters.Read.MdlAddress)</p>

<p><i>Buffer</i></p>

<p>&amp;(CallbackData-&gt;Iopb-&gt;Parameters.Read.ReadBuffer)</p>

<p><i>Length</i></p>

<p>&amp;(CallbackData-&gt;Iopb-&gt;Parameters.Read.Length)</p>

<p><i>DesiredAccess</i></p>

<p>IoWriteAccess</p>

<p> </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544645">FLT_IS_FASTIO_OPERATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544648">FLT_IS_FS_FILTER_OPERATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544673">FLT_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543371">FltLockUserBuffer</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDecodeParameters routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
