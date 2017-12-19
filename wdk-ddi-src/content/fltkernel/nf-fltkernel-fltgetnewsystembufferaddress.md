---
UID: NF.fltkernel.FltGetNewSystemBufferAddress
title: FltGetNewSystemBufferAddress function
author: windows-driver-content
description: The FltGetNewSystemBufferAddress function retrieves the AssociatedIrp.SystemBuffer buffer, which the file system has allocated. A minifilter driver's post-callback routine calls this function.
old-location: ifsk\fltgetnewsystembufferaddress.htm
old-project: ifsk
ms.assetid: 83a5e9b7-1731-422f-a0df-c1efbc8cad81
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltGetNewSystemBufferAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltGetNewSystemBufferAddress
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
---

# FltGetNewSystemBufferAddress function



## -description
The <b>FltGetNewSystemBufferAddress</b> function retrieves the AssociatedIrp.SystemBuffer buffer, which the file system has allocated. A minifilter driver's post-callback routine calls this function. 



## -syntax

````
PVOID FltGetNewSystemBufferAddress(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters

### -param CallbackData [in]

A pointer to a <a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a> structure that represents an I/O operation.


## -returns
If the AssociatedIrp.SystemBuffer buffer was allocated by the file system, <b>FltGetNewSystemBufferAddress</b> returns a pointer to this buffer; otherwise it returns <b>NULL</b>.


## -remarks
A minifilter driver's post-callback routine calls <b>FltGetNewSystemBufferAddress</b> function to retrieve a pointer to the AssociatedIrp.SystemBuffer buffer that the file system has allocated.  A minifilter driver should call this function only when the FLTFL_CALLBACK_DATA_NEW_SYSTEM_BUFFER flag is set in <i>CallbackData.Flags</i>. 

When the file system allocates its own AssociatedIrp.SystemBuffer buffer, Filter Manager will set the FLTFL_CALLBACK_DATA_NEW_SYSTEM_BUFFER flag.  This signals the minifilter that the buffer they received in the pre-operation is not the one that has the data read from the file system. 

If the FLTFL_CALLBACK_DATA_NEW_SYSTEM_BUFFER flag is not set, then this routine returns <b>NULL</b>.


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
Available in Microsoft Windows 7 and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Fltmgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetNewSystemBufferAddress function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

