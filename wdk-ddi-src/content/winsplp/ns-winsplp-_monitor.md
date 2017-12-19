---
UID: NS.WINSPLP._MONITOR
title: _MONITOR
author: windows-driver-content
description: The MONITOR structure is obsolete and is supported only for compatibility reasons.
old-location: print\monitor.htm
old-project: print
ms.assetid: 0b0dc06f-51c2-429f-a9bb-079f8a61411d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _MONITOR, LPMONITOR, MONITOR, *LPMONITOR
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
req.alt-api: MONITOR
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
req.product: Windows 10 or later.
---

# _MONITOR structure



## -description
The MONITOR structure is obsolete and is supported only for compatibility reasons. New print monitors should implement <a href="print.monitor2">MONITOR2</a> so that they can be used with print server clusters.

The MONITOR structure contains pointers to the functions defined by print monitors.



## -syntax

````
typedef struct _MONITOR {
  BOOL  (WINAPI *pfnEnumPorts)(
      LPWSTR pName, 
      DWORD Level, 
      LPBYTE pPorts, 
      DWORD cbBuf, 
      LPDWORD pcbNeeded, 
      LPDWORD pcReturned);
  BOOL  (WINAPI *pfnOpenPort)(
      LPWSTR pName, 
      PHANDLE pHandle);
  BOOL  (WINAPI *pfnOpenPortEx)(
      LPWSTR pPortName, 
      LPWSTR pPrinterName, 
      PHANDLE pHandle, 
      struct _MONITOR * pMonitor);
  BOOL  (WINAPI *pfnStartDocPort)(
      HANDLE hPort, 
      LPWSTR pPrinterName, 
      DWORD JobId, 
      DWORD Level, 
      LPBYTE pDocInfo);
  BOOL  (WINAPI *pfnWritePort)(
      HANDLE hPort, 
      LPBYTE pBuffer, 
      DWORD cbBuf, 
      LPDWORD pcbWritten);
  BOOL  (WINAPI *pfnReadPort)(
      HANDLE hPort, 
      LPBYTE pBuffer, 
      DWORD cbBuffer, 
      LPDWORD pcbRead);
  BOOL  (WINAPI *pfnEndDocPort)(HANDLE hPort);
  BOOL  (WINAPI *pfnClosePort)(HANDLE hPort);
  BOOL  (WINAPI *pfnAddPort)(
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pMonitorName);
  BOOL  (WINAPI *pfnAddPortEx)(
      LPWSTR pName, 
      DWORD Level, 
      LPBYTE lpBuffer, 
      LPWSTR pMonitorName);
  BOOL  (WINAPI *pfnConfigurePort)(
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pPortName);
  BOOL  (WINAPI *pfnDeletePort)(
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pPortName);
  BOOL  (WINAPI *pfnGetPrinterDataFromPort)(
      HANDLE hPort, 
      DWORD ControlID, 
      LPWSTR pValueName, 
      LPWSTR lpInBuffer, 
      DWORD cbInBuffer, 
      LPWSTR lpOutBuffer, 
      DWORD cbOutBuffer, 
      LPDWORD lpcbReturned);
  BOOL  (WINAPI *pfnSetPortTimeOuts)(
      HANDLE hPort, 
      LPCOMMTIMEOUTS lpCTO, 
      DWORD reserved);
  BOOL  (WINAPI *pfnXcvOpenPort)(
      LPCWSTR pszObject, 
      ACCESS_MASK GrantedAccess, 
      PHANDLE phXcv);
  DWORD (WINAPI *pfnXcvDataPort)(
      HANDLE hXcv, 
      LPCWSTR pszDataName, 
      PBYTE pInputData, 
      DWORD cbInputData, 
      PBYTE pOutputData, 
      DWORD cbOutputData, 
      PDWORD pcbOutputNeeded);
  BOOL  (WINAPI *pfnXcvClosePort)(HANDLE hXcv);
} MONITOR, *LPMONITOR;
````


## -struct-fields

### -field pfnEnumPorts

Pointer to the print monitor's <a href="print.enumports">EnumPorts</a> function. (Port monitors only.)


### -field pfnOpenPort

Pointer to the print monitor's <a href="print.openport">OpenPort</a> function.


### -field pfnOpenPortEx

Pointer to the print monitor's <a href="print.openportex">OpenPortEx</a> function. (Language monitors only.)


### -field pfnStartDocPort

Pointer to the print monitor's <a href="print.startdocport">StartDocPort</a> function.


### -field pfnWritePort

Pointer to the print monitor's <a href="print.writeport">WritePort</a> function.


### -field pfnReadPort

Pointer to the print monitor's <a href="print.readport">ReadPort</a> function.


### -field pfnEndDocPort

Pointer to the print monitor's <a href="print.enddocport">EndDocPort</a> function.


### -field pfnClosePort

Pointer to the print monitor's <a href="print.closeport">ClosePort</a> function.


### -field pfnAddPort

(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="print.addport">AddPort</a> function.


### -field pfnAddPortEx

(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="print.addportex">AddPortEx</a> function. (Port monitors only.)


### -field pfnConfigurePort

(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="print.configureport">ConfigurePort</a> function.


### -field pfnDeletePort

(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="print.deleteport">DeletePort</a> function.


### -field pfnGetPrinterDataFromPort

Pointer to the print monitor's <a href="print.getprinterdatafromport">GetPrinterDataFromPort</a> function.


### -field pfnSetPortTimeOuts

Pointer to the print monitor's <a href="print.setporttimeouts">SetPortTimeOuts</a> function. (Port monitors only.)


### -field pfnXcvOpenPort

Pointer to the print monitor's <a href="print.xcvopenport">XcvOpenPort</a> function. (Port monitors only.)


### -field pfnXcvDataPort

Pointer to the print monitor's <a href="print.xcvdataport">XcvDataPort</a> function. (Port monitors only.)


### -field pfnXcvClosePort

Pointer to the print monitor's <a href="print.xcvcloseport">XcvClosePort</a> function. (Port monitors only.)


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<a href="print.monitorui">MONITORUI</a>
</dt>
<dt>
<a href="print.monitor2">MONITOR2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MONITOR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

