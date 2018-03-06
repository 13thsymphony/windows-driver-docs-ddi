---
UID: NF:wiamdef.WIAS_LWARNING
title: WIAS_LWARNING macro
author: windows-driver-content
description: The WIAS_LWARNING macro is obsolete for Windows Vista and later.The WIAS_LWARNING macro writes a diagnostic WIA_WARNING message to the log file.
old-location: image\wias_lwarning.htm
old-project: image
ms.assetid: 2959c470-1da7-4396-a591-7a356379f9de
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWiaLog_bac21803-be4c-4ce0-a241-b9380cb627ab.xml, WIAS_LWARNING, WIAS_LWARNING macro [Imaging Devices], image.wias_lwarning, wiamdef/WIAS_LWARNING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiamdef.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later. Obsolete for Windows Vista and later.
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
req.lib: wiamdef.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wiamdef.h
api_name:
-	WIAS_LWARNING
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# WIAS_LWARNING function
The WIAS_LWARNING macro is obsolete for Windows Vista and later.

The WIAS_LWARNING macro writes a diagnostic WIA_WARNING message to the log file.

## Syntax

````
WIAS_LERROR( WIAS_LWARNING(
         IWiaLog   *pIWiaLog,
         LONG      lResId,
   const CHAR      *format_string, ...
);
````

## Parameters

`pILog`

TBD

`ResID`

TBD

`Args`

TBD


## Return Value

None

## Remarks

The following is an example of how the macro can be used:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WIAS_LWARNING(g_pIWiaLog, WIALOG_NO_RESOURCE_ID,
  ("MyClass::MyMethod, This is my text and my lValue = %d", lValue));</pre>
</td>
</tr>
</table></span></div>
Please note that it does not write to the new log file used in Windows Vista and later.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me, Windows XP, and later. Obsolete for Windows Vista and later.  |
| **Target Platform** | Desktop |
| **Header** | wiamdef.h (include Wiautil.h) |
| **Library** | wiamdef.h |

## See Also

<a href="..\wiamdef\nf-wiamdef-wias_ltrace.md">WIAS_LTRACE</a>



<a href="..\wiamdef\nf-wiamdef-wias_lhresult.md">WIAS_LHRESULT</a>



<a href="..\wiamdef\nf-wiamdef-wias_lerror.md">WIAS_LERROR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_LWARNING macro%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>