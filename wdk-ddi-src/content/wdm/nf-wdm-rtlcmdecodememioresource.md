---
UID: NF.wdm.RtlCmDecodeMemIoResource
title: RtlCmDecodeMemIoResource function
author: windows-driver-content
description: The RtlCmDecodeMemIoResource routine provides the starting address and length of a CM_PARTIAL_RESOURCE_DESCRIPTOR structure that describes a range of memory or I/O port addresses.
old-location: kernel\rtlcmdecodememioresource.htm
old-project: kernel
ms.assetid: cc2394ce-128e-46a2-8688-a71851af06cf
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlCmDecodeMemIoResource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlCmDecodeMemIoResource
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
req.product: Windows 10 or later.
---

# RtlCmDecodeMemIoResource function



## -description
The <b>RtlCmDecodeMemIoResource</b> routine provides the starting address and length of a <a href="kernel.cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes a range of memory or I/O port addresses. 



## -syntax

````
ULONGLONG RtlCmDecodeMemIoResource(
  _In_      PCM_PARTIAL_RESOURCE_DESCRIPTOR Descriptor,
  _Out_opt_ PULONGLONG                      Start
);
````


## -parameters

### -param Descriptor [in]

A pointer to the <a href="kernel.cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure to provide the starting address and length for.


### -param Start [out, optional]

A pointer to a variable that receives the starting address of the range of memory or I/O port addresses.


## -returns
<b>RtlCmDecodeMemIoResource</b> returns the length of the address range, in bytes.


## -remarks
The <b>Type</b> member of the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure must be <b>CmResourceTypeMemory</b>, <b>CmResourceTypeMemoryLarge</b>, or <b>CmResourceTypePort</b>. 


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
Available in Windows Vista and later versions of Windows.

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
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="kernel.rtlcmencodememioresource">RtlCmEncodeMemIoResource</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCmDecodeMemIoResource routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

