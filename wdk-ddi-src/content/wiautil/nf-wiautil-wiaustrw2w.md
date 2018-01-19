---
UID : NF:wiautil.wiauStrW2W
title : wiauStrW2W function
author : windows-driver-content
description : The wiauStrW2W function copies a Unicode string to another Unicode string.
old-location : image\wiaustrw2w.htm
old-project : image
ms.assetid : 84f6d47f-bd14-4df4-b4fa-e58412daba6f
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : wiauStrW2W
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
req.alt-api : wiauStrW2W
req.alt-loc : wiautil.h
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
req.typenames : SKIP_AMOUNT
req.product : Windows 10 or later.
---


# wiauStrW2W function
The <b>wiauStrW2W</b> function copies a Unicode string to another Unicode string.

## Syntax

````
HRESULT _stdcall wiauStrW2W(
  _In_  WCHAR *pwszSrc,
  _Out_ WCHAR *pwszDst,
        INT   iSize
);
````

## Parameters

`pwszSrc`

Points to the Unicode string to be copied.

`pwszDst`

Pointer to a memory location that receives the copied string.

`iSize`

Specifies the size, in bytes, of the buffer pointed to by <i>pwszDst</i>.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wiautil\nf-wiautil-wiaustrc2c.md">wiauStrC2C</a>
</dt>
<dt>
<a href="..\wiautil\nf-wiautil-wiaustrc2w.md">wiauStrC2W</a>
</dt>
<dt>
<a href="..\wiautil\nf-wiautil-wiaustrw2c.md">wiauStrW2C</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauStrW2W function%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>