---
UID : NS:aux_klib._KBUGCHECK_DATA
title : "_KBUGCHECK_DATA"
author : windows-driver-content
description : The KBUGCHECK_DATA structure contains bug check parameters.
old-location : kernel\kbugcheck_data.htm
old-project : kernel
ms.assetid : 9fecf57b-e77a-458e-80ce-118eed2d48b4
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PKBUGCHECK_DATA structure pointer [Kernel-Mode Driver Architecture], aux_klib_ced3c2df-3d09-45d8-8ae8-049d2bc46160.xml, KBUGCHECK_DATA structure [Kernel-Mode Driver Architecture], kernel.kbugcheck_data, _KBUGCHECK_DATA, KBUGCHECK_DATA, PKBUGCHECK_DATA, aux_klib/KBUGCHECK_DATA, *PKBUGCHECK_DATA, aux_klib/PKBUGCHECK_DATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : aux_klib.h
req.include-header : Aux_klib.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KBUGCHECK_DATA, *PKBUGCHECK_DATA
---

# _KBUGCHECK_DATA structure
The <b>KBUGCHECK_DATA</b> structure contains bug check parameters.

## Syntax
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

## Members


`BugCheckCode`

The bug check code. This value identifies that type of bug check that has occurred.

`BugCheckDataSize`

The size, in bytes, of the <b>KBUGCHECK_DATA</b> structure. Callers of <a href="..\aux_klib\nf-aux_klib-auxklibgetbugcheckdata.md">AuxKlibGetBugCheckData</a> must supply this value.

`Parameter1`

Bug check parameter 1. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>.

`Parameter2`

Bug check parameter 2. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>.

`Parameter3`

Bug check parameter 3. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>.

`Parameter4`

Bug check parameter 4. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>.

## Remarks
The <b>KBUGCHECK_DATA</b> structure is used as a parameter to <a href="..\aux_klib\nf-aux_klib-auxklibgetbugcheckdata.md">AuxKlibGetBugCheckData</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | aux_klib.h (include Aux_klib.h) |

## See Also

<a href="..\aux_klib\nf-aux_klib-auxklibgetbugcheckdata.md">AuxKlibGetBugCheckData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KBUGCHECK_DATA structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>