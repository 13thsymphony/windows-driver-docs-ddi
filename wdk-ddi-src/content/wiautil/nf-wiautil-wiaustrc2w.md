---
UID : NF:wiautil.wiauStrC2W
title : wiauStrC2W function
author : windows-driver-content
description : The wiauStrC2W function converts an ANSI character string to a Unicode string.
old-location : image\wiaustrc2w.htm
old-project : image
ms.assetid : 66d90248-c496-44c8-98f4-5eb3e2cae130
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wiautil/wiauStrC2W, wiauStrC2W, wiauStrC2W function [Imaging Devices], image.wiaustrc2w, wiauFncs_acd27425-a431-42a0-8317-514ea7904ace.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wiautil.h
req.include-header : Wiautil.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows XP and later.
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SKIP_AMOUNT
req.product : Windows 10 or later.
---


# wiauStrC2W function
The <b>wiauStrC2W</b> function converts an ANSI character string to a Unicode string.

## Syntax

````
HRESULT _stdcall wiauStrC2W(
  _In_  CHAR  *pszSrc,
  _Out_ WCHAR *pwszDst,
        INT   iSize
);
````

## Parameters

`pszSrc`

Points to the ANSI string to convert.

`pwszDst`

Pointer to a memory location that receives the converted Unicode string.

`iSize`

Specifies the size, in bytes, of the buffer pointed to by <i>pwszDst</i>.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later. Available in Windows XP and later. |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wiautil\nf-wiautil-wiaustrw2c.md">wiauStrW2C</a>

<a href="..\wiautil\nf-wiautil-wiaustrc2c.md">wiauStrC2C</a>

<a href="..\wiautil\nf-wiautil-wiaustrw2w.md">wiauStrW2W</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauStrC2W function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>