---
UID: NF:wiamdef.WIAS_ERROR
title: WIAS_ERROR macro
author: windows-driver-content
description: The WIAS_ERROR macro writes a diagnostic message to the Wiatrace.log file.
old-location: image\wias_error.htm
old-project: image
ms.assetid: e439f130-1b99-4f46-ace5-3456c09a5f67
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WIAS_ERROR macro [Imaging Devices], WIAS_ERROR, wiamdef/WIAS_ERROR, image.wias_error, IWiaLog_5b3e0d61-e0e5-4385-8256-943e437cee9d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiamdef.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiamdef.h
apiname:
-	WIAS_ERROR
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# WIAS_ERROR function
The WIAS_ERROR macro writes a diagnostic message to the <i>Wiatrace.log</i> file.

## Syntax

````
WIAS_ERROR( WIAS_ERROR(
         HInst  HInst,
   const CHAR   *format_string, ...
);
````

## Parameters

`x`

TBD


## Return Value

None

## Remarks

This macro is the recommended way to implement error logging on Windows Vista, because unlike <a href="..\wiamdef\nf-wiamdef-wias_ltrace.md">WIAS_LERROR</a>, WIA_ERROR allows error messages to be written to the log file (<i>Wiatrace.log</i>). The <i>Wiatrace.log</i> file is only available in Windows Vista and later versions of the operating system. The utility used to view the contents of this log file is WiaTrcVw.exe.

To enable tracing in free builds, drivers must define the WIA_DEBUG macro by adding <code>#define WIA_DEBUG</code> before including any of the WIA headers. Tracing is enabled by default in checked and debug builds of the operating system.

The following is an example of how the macro can be used:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WIAS_ERROR((g_hInst, "Failed to read (%ws) entry under %ws section of device registry",REG_ENTRY_STORAGEPATH,REG_ENTRY_DEVICEDATA));</pre>
</td>
</tr>
</table></span></div>
This code snippet was taken from <i>Wiadriver.cpp</i>, which is included with the WDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the operating system.  |
| **Target Platform** | Desktop |
| **Header** | wiamdef.h |
| **Library** | wiamdef.h |

## See Also

<a href="..\wiamdef\nf-wiamdef-wias_trace.md">WIAS_TRACE</a>



<a href="..\wiamdef\nf-wiamdef-wias_hresult.md">WIAS_HRESULT</a>



<a href="..\wiamdef\nf-wiamdef-wias_assert.md">WIAS_ASSERT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_ERROR macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>