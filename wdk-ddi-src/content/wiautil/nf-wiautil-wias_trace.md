---
UID: NF:wiautil.WIAS_TRACE
title: WIAS_TRACE macro
author: windows-driver-content
description: The WIAS_TRACE macro writes a diagnostic message to the Wiatrace.log file.
old-location: image\wias_trace.htm
old-project: image
ms.assetid: 9f6b06bf-60d3-4ec2-8c49-405bff2ccb5e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IWiaLog_c755ea6c-c312-4b15-be83-a437358b83a9.xml, WIAS_TRACE, WIAS_TRACE macro [Imaging Devices], image.wias_trace, wiamdef/WIAS_TRACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
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
-	WIAS_TRACE
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# WIAS_TRACE function
The WIAS_TRACE macro writes a diagnostic message to the <i>Wiatrace.log</i> file.

## Syntax

````
WIAS_ERROR( WIAS_TRACE(
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

To enable tracing in free builds, drivers must define the WIA_DEBUG macro by adding <code>#define WIA_DEBUG</code> before including any of the WIA headers. Tracing is enabled by default in checked and debug builds of the operating system.

The following is an example of how the macro would be used:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WIAS_TRACE((g_hInst,"WIA storage path = %ws",m_wszStoragePath));</pre>
</td>
</tr>
</table></span></div>
This code snippet was taken from <i>Wiadriver.cpp</i>, which is included with the WDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |

## See Also

<a href="..\wiautil\nf-wiautil-wias_assert.md">WIAS_ASSERT</a>



<a href="..\wiautil\nf-wiautil-wias_error.md">WIAS_ERROR</a>



<a href="..\wiautil\nf-wiautil-wias_hresult.md">WIAS_HRESULT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_TRACE macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>