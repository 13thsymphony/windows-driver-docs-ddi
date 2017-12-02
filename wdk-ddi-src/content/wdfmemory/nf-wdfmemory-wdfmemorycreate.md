---
UID: NF.wdfmemory.WdfMemoryCreate
title: WdfMemoryCreate
author: windows-driver-content
description: The WdfMemoryCreate method creates a framework memory object and allocates a memory buffer of a specified size.
old-location: wdf\wdfmemorycreate.htm
old-project: wdf
ms.assetid: d2071ea0-737d-4a61-90d6-614d77983f0b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfMemoryCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfMemoryCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, ParentObjectCheck
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: See Remarks section.
req.iface: 
req.product: Windows 10 or later.
---

# WdfMemoryCreate function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfMemoryCreate</b> method creates a framework memory object and allocates a memory buffer of a specified size. </p>


## -syntax

````
NTSTATUS WdfMemoryCreate(
  _In_opt_  PWDF_OBJECT_ATTRIBUTES Attributes,
  _In_      POOL_TYPE              PoolType,
  _In_opt_  ULONG                  PoolTag,
  _In_      size_t                 BufferSize,
  _Out_     WDFMEMORY              *Memory,
  _Out_opt_ PVOID                  *Buffer
);
````


## -parameters
<dl>

### -param Attributes [in, optional]

<dd>
<p>A pointer to a <a href="..\wdfobject\ns-wdfobject--wdf-object-attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the new memory object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.</p>
</dd>

### -param PoolType [in]

<dd>
<p>A <a href="..\wdm\ne-wdm--pool-type.md">POOL_TYPE</a>-typed value that specifies the type of memory to be allocated. </p>
</dd>

### -param PoolTag [in, optional]

<dd>
<p>A driver-defined pool tag for the allocated memory. Debuggers display this tag. Drivers typically specify a character string of up to four characters, delimited by single quotation marks, in reverse order (for example, 'dcba'). The ASCII value of each character in the tag must be between 0 and 127. Debugging your driver is easier if each pool tag is unique. </p>
<p>If <i>PoolTag</i> is zero, the framework provides a default pool tag that uses the first four characters of your driver's kernel-mode service name. If the service name begins with "WDF" (the name is not case sensitive and does not include the quotation marks), the next four characters are used. If fewer than four characters are available, "FxDr" is used. </p>
<p>For KMDF versions 1.5 and later, your driver can use the <b>DriverPoolTag</b> member of the <a href="..\wdfdriver\ns-wdfdriver--wdf-driver-config.md">WDF_DRIVER_CONFIG</a> structure to specify a default pool tag.</p>
</dd>

### -param BufferSize [in]

<dd>
<p>The nonzero specified size, in bytes, of the buffer. </p>
</dd>

### -param Memory [out]

<dd>
<p>A pointer to a location that receives a handle to the new memory object.</p>
</dd>

### -param Buffer [out, optional]

<dd>
<p>A pointer to a location that receives a pointer to the buffer that is associated with the new memory object. This parameter is optional and can be <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p><b>WdfMemoryCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>An invalid parameter was detected.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>There was insufficient memory.</p>

<p> </p>

<p>For a list of other return values that the <b>WdfMemoryCreate</b> method might return, see <a href="wdf.framework_object_creation_errors">Framework Object Creation Errors</a>.

</p>

<p>This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.</p>

## -remarks
<p>The <b>WdfMemoryCreate</b> method allocates a buffer of the size that the <i>BufferSize</i> parameter specifies and creates a framework memory object that represents the buffer. </p>

<p>To obtain the buffer's address, your driver can supply a non-<b>NULL</b> value for the <b>WdfMemoryCreate</b> function's <i>Buffer</i> parameter, or the driver can call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>.</p>

<p>The default parent object for each memory object is the framework driver object that represents the driver that called <b>WdfMemoryCreate</b>. If your driver creates a memory object that it uses with a specific device object, request object, or other framework object, it should set the memory object's parent appropriately. The memory object and its buffer will be deleted when the parent object is deleted. If you do not change the default parent object, the memory object and its buffer will remain until the I/O manager unloads your driver. </p>

<p>A driver can also delete a memory object and its buffer by calling <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>.</p>

<p>If <i>BufferSize</i> is less than PAGE_SIZE, the operating system gives the caller exactly the number of requested bytes of memory. The buffer is not necessarily page-aligned, but it is aligned by the number of bytes that the MEMORY_ALLOCATION_ALIGNMENT constant specifies in <i>Ntdef.h</i>. Buffers of PAGE_SIZE or less do not cross page boundaries. </p>

<p>If <i>BufferSize</i> is PAGE_SIZE or greater, the system allocates a page-aligned buffer. If the <i>PoolType</i> parameter is <b>NonPagedPool</b>, the system allocates the number of pages that are necessary to hold all of the bytes. Any unused bytes on the last-allocated page are essentially wasted.</p>

<p>For more information about framework memory objects, see <a href="wdf.using_memory_buffers">Using Memory Buffers</a>.</p>

<p>If your driver specifies <b>PagedPool</b> for <i>PoolType</i>, the <b>WdfMemoryCreate</b> method must be called at IRQL &lt;= APC_LEVEL. Otherwise, the method can be called at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>The following code example creates a framework memory object and allocates a buffer whose size is WRITE_BUFFER_SIZE. The memory object's parent is a request object. </p>

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
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfmemory.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>See Remarks section.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_parentobjectcheck">ParentObjectCheck</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ne-wdm--pool-type.md">POOL_TYPE</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject--wdf-object-attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfobject\nf-wdfobject-wdf-object-attributes-init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatefromlookaside.md">WdfMemoryCreateFromLookaside</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>
</dt>
<dt>
<a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfMemoryCreate method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
