---
UID: NF:wia_lh.IWiaLog.Log
title: IWiaLog::Log method
author: windows-driver-content
description: The IWiaLog interface is obsolete for Windows XP and later, and is no longer supported. Use the Diagnostic Log Macros instead.The IWiaLog::Log method writes a diagnostic log message to Wiaservc.log.
old-location: image\iwialog_log.htm
old-project: image
ms.assetid: bca012b4-76ae-4ba5-99b4-92a367774de7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: Log method [Imaging Devices], Log method [Imaging Devices], IWiaLog interface, Log, wia_lh/IWiaLog::Log, image.iwialog_log, IWiaLog interface [Imaging Devices], Log method, IWiaLog_e3605b5e-0494-46a7-85c1-3a0707a74764.xml, IWiaLog, IWiaLog::Log
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wia_lh.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later. Obsoletefor Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros.
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
req.lib: wia_lh.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wia_lh.h
apiname:
-	IWiaLog.Log
product: Windows
targetos: Windows
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---


# Log method
The <b>IWiaLog</b> interface is obsolete for Windows XP and later, and is no longer supported. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540599">Diagnostic Log Macros</a> instead.The <b>IWiaLog::Log</b> method writes a diagnostic log message to <i>Wiaservc.log</i>.

## Syntax

````
HRESULT Log(
  [in] LONG lFlags,
  [in] LONG lResId,
  [in] LONG lDetail,
  [in] BSTR bstrText
);
````

## Parameters

`lFlags`

Specifies the type of diagnostic message. This parameter can be WIA_WARNING, WIA_TRACE or WIA_ERROR.

`lResID`



`lDetail`

Specifies the diagnostic detail level of the message. This parameter can be one of the following values.

<table>
<tr>
<th>Level</th>
<th>Description</th>
</tr>
<tr>
<td>
WIALOG_LEVEL1

</td>
<td>
Logs entry and exit points for all WIA methods and functions.

</td>
</tr>
<tr>
<td>
WIALOG_LEVEL2

</td>
<td>
Logs additional details for WIALOG_LEVEL1.

</td>
</tr>
<tr>
<td>
WIALOG_LEVEL3

</td>
<td>
Logs entry and exit points for all WIA methods and functions and additional vendor-supplied functions.

</td>
</tr>
<tr>
<td>
WIALOG_LEVEL4

</td>
<td>
Logs additional details for WIALOG_LEVEL3. 

</td>
</tr>
<tr>
<td>
WIALOG_LEVELXXX

</td>
<td>
User-defined log levels.

</td>
</tr>
</table>

`bstrText`

Specifies the error text. The error text should be prefixed with the full name of the method or function and generate the message in the format of "class::method, error-text".


## Return Value

If the method succeeds, it returns S_OK.  If the method fails, it returns a standard COM error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me, Windows XP, and later. Obsoletefor Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros.  |
| **Target Platform** | Desktop |
| **Header** | wia_lh.h |
| **Library** | wia_lh.h |