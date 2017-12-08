---
UID: NS.WDM._OB_PRE_DUPLICATE_HANDLE_INFORMATION
title: _OB_PRE_DUPLICATE_HANDLE_INFORMATION
author: windows-driver-content
description: The OB_PRE_DUPLICATE_HANDLE_INFORMATION structure provides information to an ObjectPreCallback routine about a thread or process handle that is being duplicated.
old-location: kernel\ob_pre_duplicate_handle_information.htm
old-project: kernel
ms.assetid: f2798729-98a2-44b6-94a6-180bb4db96cb
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _OB_PRE_DUPLICATE_HANDLE_INFORMATION, *POB_PRE_DUPLICATE_HANDLE_INFORMATION, OB_PRE_DUPLICATE_HANDLE_INFORMATION
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
req.alt-api: OB_PRE_DUPLICATE_HANDLE_INFORMATION
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

# _OB_PRE_DUPLICATE_HANDLE_INFORMATION structure



## -description
The <b>OB_PRE_DUPLICATE_HANDLE_INFORMATION</b> structure provides information to an <a href="kernel.objectprecallback">ObjectPreCallback</a> routine about a thread or process handle that is being duplicated.


## -syntax

````
typedef struct _OB_PRE_DUPLICATE_HANDLE_INFORMATION {
  ACCESS_MASK DesiredAccess;
  ACCESS_MASK OriginalDesiredAccess;
  PVOID       SourceProcess;
  PVOID       TargetProcess;
} OB_PRE_DUPLICATE_HANDLE_INFORMATION, *POB_PRE_DUPLICATE_HANDLE_INFORMATION;
````


## -struct-fields

### -field DesiredAccess

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the access rights to grant for the handle. By default, this member equals <i>OriginalDesiredAccess</i>, but the <i>ObjectPreCallback</i> routine can modify this value to restrict the access that is granted. For a description of the access rights that drivers can use, see <a href="kernel.ob_pre_create_handle_information">OB_PRE_CREATE_HANDLE_INFORMATION</a>.

### -field OriginalDesiredAccess

An ACCESS_MASK value that specifies the original access that was requested for the handle.

### -field SourceProcess

A pointer to the process object for the process that is the source of the handle.

### -field TargetProcess

A pointer to the process object for the process that receives the duplicated handle. 

## -remarks
You can never add access rights beyond what is specified in the <b>DesiredAccess</b> member. If the access right is listed as a modifiable flag, the access right can be removed.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="kernel.objectprecallback">ObjectPreCallback</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20OB_PRE_DUPLICATE_HANDLE_INFORMATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
