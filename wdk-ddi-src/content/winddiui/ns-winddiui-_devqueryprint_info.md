---
UID: NS.WINDDIUI._DEVQUERYPRINT_INFO
title: _DEVQUERYPRINT_INFO
author: windows-driver-content
description: The DEVQUERYPRINT_INFO structure is used as an input parameter to a printer interface DLL's DevQueryPrintEx function.
old-location: print\devqueryprint_info.htm
old-project: print
ms.assetid: c46193f2-4c69-4aed-a063-2225faba9ee1
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _DEVQUERYPRINT_INFO, PDEVQUERYPRINT_INFO, *PDEVQUERYPRINT_INFO, DEVQUERYPRINT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winddiui.h
req.include-header: Winddiui.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEVQUERYPRINT_INFO
req.alt-loc: winddiui.h
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
req.product: Windows 10 or later.
---

# _DEVQUERYPRINT_INFO structure



## -description
The DEVQUERYPRINT_INFO structure is used as an input parameter to a printer interface DLL's <a href="print.devqueryprintex">DevQueryPrintEx</a> function.



## -syntax

````
typedef struct _DEVQUERYPRINT_INFO {
  WORD    cbSize;
  WORD    Level;
  HANDLE  hPrinter;
  DEVMODE *pDevMode;
  LPWSTR  pszErrorStr;
  DWORD   cchErrorStr;
  DWORD   cchNeeded;
} DEVQUERYPRINT_INFO, *PDEVQUERYPRINT_INFO;
````


## -struct-fields

### -field cbSize

Spooler-supplied size, in bytes, of the DEVQUERYPRINT_INFO structure.


### -field Level

Spooler-supplied level of the DEVQUERYPRINT_INFO structure. Currently, this member is always set to 1.


### -field hPrinter

Spooler-supplied printer handle.


### -field pDevMode

Spooler-supplied pointer to a <a href="display.devmodew">DEVMODEW</a> structure describing printer characteristics required by the print job.


### -field pszErrorStr

Spooler-supplied pointer to a buffer to receive a NULL-terminated error text string, if the print job cannot be printed.


### -field cchErrorStr

Spooler-supplied size, in bytes, of the string buffer pointed to by <b>pszErrorStr</b>.


### -field cchNeeded

Driver-supplied length, in bytes, of the error string supplied in the buffer pointed to by <b>pszErrorStr</b>. If the string is too large to fit in the buffer, the string should be truncated, but the untruncated length should be specified here.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winddiui.h (include Winddiui.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.devqueryprintex">DevQueryPrintEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DEVQUERYPRINT_INFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

