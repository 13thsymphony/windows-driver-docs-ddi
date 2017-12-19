---
UID: NS.AUX_KLIB._KBUGCHECK_DATA
title: _KBUGCHECK_DATA
author: windows-driver-content
description: The KBUGCHECK_DATA structure contains bug check parameters.
old-location: kernel\kbugcheck_data.htm
old-project: kernel
ms.assetid: 9fecf57b-e77a-458e-80ce-118eed2d48b4
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _KBUGCHECK_DATA, KBUGCHECK_DATA, PKBUGCHECK_DATA, *PKBUGCHECK_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KBUGCHECK_DATA
req.alt-loc: aux_klib.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _KBUGCHECK_DATA structure



## -description
The <b>KBUGCHECK_DATA</b> structure contains bug check parameters.



## -syntax

````
typedef struct _KBUGCHECK_DATA {
  ULONG     BugCheckDataSize;
  ULONG     BugCheckCode;
  ULONG_PTR Parameter1;
  ULONG_PTR Parameter2;
  ULONG_PTR Parameter3;
  ULONG_PTR Parameter4;
} KBUGCHECK_DATA, *PKBUGCHECK_DATA;
````


## -struct-fields

### -field BugCheckDataSize

The size, in bytes, of the <b>KBUGCHECK_DATA</b> structure. Callers of <a href="kernel.auxklibgetbugcheckdata">AuxKlibGetBugCheckData</a> must supply this value. 


### -field BugCheckCode

The bug check code. This value identifies that type of bug check that has occurred.


### -field Parameter1

Bug check parameter 1. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>. 


### -field Parameter2

Bug check parameter 2. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>. 


### -field Parameter3

Bug check parameter 3. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>. 


### -field Parameter4

Bug check parameter 4. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>. 


## -remarks
The <b>KBUGCHECK_DATA</b> structure is used as a parameter to <a href="kernel.auxklibgetbugcheckdata">AuxKlibGetBugCheckData</a>. 


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.auxklibgetbugcheckdata">AuxKlibGetBugCheckData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KBUGCHECK_DATA structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

