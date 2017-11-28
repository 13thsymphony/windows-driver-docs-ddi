---
UID: NS.winsplp._MONITORUI
title: MONITORUI
author: windows-driver-content
description: The MONITORUI structure contains pointers to the functions within a port monitor UI DLL that the print spooler calls.
old-location: print\monitorui.htm
old-project: print
ms.assetid: c6701ca4-f3ce-40b9-8582-d70e8b2acde3
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: MONITORUI, MONITORUI, *PMONITORUI
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MONITORUI
req.alt-loc: winsplp.h
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
req.iface: 
req.product: Windows 10 or later.
---

# MONITORUI structure



## -description
<p>The MONITORUI structure contains pointers to the functions within a port monitor UI DLL that the print spooler calls.</p>


## -syntax

````
typedef struct _MONITORUI {
  DWORD dwMonitorUISize;
  BOOL  (WINAPI *pfnAddPortUI)(
      _In_opt_ PCWSTR pszServer, 
      _In_ HWND hWnd, 
      _In_ PCWSTR pszMonitorNameIn, 
      _Out_opt_ PWSTR ppszPortNameOut);
  BOOL  (WINAPI *pfnConfigurePortUI)(
      _In_opt_ PCWSTR pName, 
      _In_ HWND hWnd, 
      _In_ PCWSTR pPortName);
  BOOL  (WINAPI *pfnDeletePortUI)(
      _In_opt_ PCWSTR pszServer, 
      _In_ HWND hWnd, 
      _In_ PCWSTR pszPortName);
} MONITORUI, *PMONITORUI;
````


## -struct-fields
<dl>

### -field <b>dwMonitorUISize</b>

<dd>
<p>Size, in bytes, of the MONITORUI structure.</p>
</dd>

### -field <b>pfnAddPortUI</b>

<dd></dd>

### -field <b>pfnConfigurePortUI</b>

<dd></dd>

### -field <b>pfnDeletePortUI</b>

<dd></dd>
</dl>

## -remarks
<p>All structure members must be initialized by the port monitor UI DLL. The structure's address is passed to the print spooler as the return value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551608">InitializePrintMonitorUI</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Winsplp.h (include Winsplp.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551608">InitializePrintMonitorUI</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MONITORUI structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
