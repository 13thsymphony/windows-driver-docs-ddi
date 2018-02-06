---
UID: NF:wiautil.wiauStrC2C
title: wiauStrC2C function
author: windows-driver-content
description: The wiauStrC2C function copies an ANSI character string to another ANSI character string.
old-location: image\wiaustrc2c.htm
old-project: image
ms.assetid: 7e8cd99a-d1b1-4261-9643-4a84bddfdc01
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: image.wiaustrc2c, wiauStrC2C function [Imaging Devices], wiauFncs_2266a6c9-ed4b-4af8-947a-d634bd9e9912.xml, wiauStrC2C, wiautil/wiauStrC2C
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiautil.h
apiname:
-	wiauStrC2C
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauStrC2C function
The <b>wiauStrC2C</b> function copies an ANSI character string to another ANSI character string.

## Syntax

````
HRESULT _stdcall wiauStrC2C(
  _In_  CHAR *pszSrc,
  _Out_ CHAR *pszDst,
        INT  iSize
);
````

## Parameters

`pszSrc`

Points to the ANSI string to be copied.

`pszDst`

Pointer to a memory location that receives the copied string

`iSize`

Specifies the size, in bytes, of the buffer pointed to by <i>pszDst</i>.


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

<a href="..\wiautil\nf-wiautil-wiaustrw2w.md">wiauStrW2W</a>

<a href="..\wiautil\nf-wiautil-wiaustrw2c.md">wiauStrW2C</a>

<a href="..\wiautil\nf-wiautil-wiaustrc2w.md">wiauStrC2W</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauStrC2C function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>