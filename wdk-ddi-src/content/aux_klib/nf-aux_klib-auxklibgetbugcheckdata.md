---
UID: NF.aux_klib.AuxKlibGetBugCheckData
title: AuxKlibGetBugCheckData function
author: windows-driver-content
description: The AuxKlibGetBugCheckData routine retrieves information about a bug check that has just occurred.
old-location: kernel\auxklibgetbugcheckdata.htm
old-project: kernel
ms.assetid: d41d0eba-14e3-48ff-874d-e52589cf716c
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: AuxKlibGetBugCheckData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Universal
req.target-min-winverclnt: Supported starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AuxKlibGetBugCheckData
req.alt-loc: Aux_Klib.lib,Aux_Klib.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Aux_Klib.lib
req.dll: 
req.irql: 
---

# AuxKlibGetBugCheckData function



## -description
The <b>AuxKlibGetBugCheckData</b> routine retrieves information about a bug check that has just occurred.



## -syntax

````
NTSTATUS AuxKlibGetBugCheckData(
  _Out_ PKBUGCHECK_DATA BugCheckData
);
````


## -parameters

### -param BugCheckData [out]

A pointer to a <a href="kernel.kbugcheck_data">KBUGCHECK_DATA</a> structure that contains information about the bug check. The <i>BugCheckData</i> size of this structure should be set equal to the size, in bytes, of the <b>KBUGCHECK_DATA</b> structure.


## -returns
<b>AuxKlibGetBugCheckData</b> returns STATUS_SUCCESS if the operation succeeds. The routine returns STATUS_INFO_LENGTH_MISMATCH if the <b>KBUGCHECK_DATA</b> structure's size is incorrect.


## -remarks
The <b>AuxKlibGetBugCheckData</b> routine can be called only from a <a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a> routine.

Drivers must call <a href="kernel.auxklibinitialize">AuxKlibInitialize</a> before calling <b>AuxKlibGetBugCheckData</b>.


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
Supported starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Aux_klib.h (include Aux_klib.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Aux_Klib.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.auxklibinitialize">AuxKlibInitialize</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a>
</dt>
<dt>
<a href="kernel.kbugcheck_data">KBUGCHECK_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AuxKlibGetBugCheckData routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

