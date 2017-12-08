---
UID: NS.winsplp._MONITOR2
title: MONITOR2
author: windows-driver-content
description: The MONITOR2 structure contains pointers to the functions defined by print monitors.
old-location: print\monitor2.htm
old-project: print
ms.assetid: 0bfb5119-2034-4e63-9fbe-e2ff42a352d6
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: MONITOR2,
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
req.alt-api: MONITOR2
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

# MONITOR2 structure



## -description
<p>The MONITOR2 structure contains pointers to the functions defined by print monitors.</p>


## -syntax

````
typedef struct _MONITOR2 {
  DWORD cbSize;
  BOOL  (WINAPI *pfnEnumPorts)(
      HANDLE hMonitor, 
      LPWSTR pName, 
      DWORD Level, 
      LPBYTE pPorts, 
      DWORD cbBuf, 
      LPDWORD pcbNeeded, 
      LPDWORD pcReturned);
  BOOL  (WINAPI *pfnOpenPort)(
      HANDLE hMonitor, 
      LPWSTR pName, 
      PHANDLE pHandle);
  BOOL  (WINAPI *pfnOpenPortEx)(
      HANDLE hMonitor, 
      HANDLE hMonitorPort, 
      LPWSTR pPortName, 
      LPWSTR pPrinterName, 
      PHANDLE pHandle, 
      struct _MONITOR2 * pMonitor2);
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
      HANDLE hMonitor, 
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pMonitorName);
  BOOL  (WINAPI *pfnAddPortEx)(
      HANDLE hMonitor, 
      LPWSTR pName, 
      DWORD Level, 
      LPBYTE lpBuffer, 
      LPWSTR pMonitorName);
  BOOL  (WINAPI *pfnConfigurePort)(
      HANDLE hMonitor, 
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pPortName);
  BOOL  (WINAPI *pfnDeletePort)(
      HANDLE hMonitor, 
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
      HANDLE hMonitor, 
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
  VOID  (WINAPI *pfnShutdown)(HANDLE hMonitor);
  DWORD (WINAPI *pfnSendRecvBidiDataFromPort)(
      HANDLE hPort, 
      DWORD dwAccessBit, 
      LPCWSTR pAction, 
      PBIDI_REQUEST_CONTAINER pReqData, 
      PBIDI_RESPONSE_CONTAINER* ppResData);
} MONITOR2, *PMONITOR2, *LPMONITOR2;
````


## -struct-fields
<dl>

### -field cbSize

<dd>
<p>Specifies the size, in bytes, of the MONITOR2 structure.</p>
</dd>

### -field pfnEnumPorts

<dd>
<p>Pointer to the print monitor's <a href="print.enumports">EnumPorts</a> function. (Port monitors only.)</p>
</dd>

### -field pfnOpenPort

<dd>
<p>Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a> function.</p>
</dd>

### -field pfnOpenPortEx

<dd>
<p>Pointer to the print monitor's <a href="print.openportex">OpenPortEx</a> function. (Language monitors only.)</p>
</dd>

### -field pfnStartDocPort

<dd>
<p>Pointer to the print monitor's <a href="print.startdocport">StartDocPort</a> function.</p>
</dd>

### -field pfnWritePort

<dd>
<p>Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-writeport.md">WritePort</a> function.</p>
</dd>

### -field pfnReadPort

<dd>
<p>Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-readport.md">ReadPort</a> function.</p>
</dd>

### -field pfnEndDocPort

<dd>
<p>Pointer to the print monitor's <a href="print.enddocport">EndDocPort</a> function.</p>
</dd>

### -field pfnClosePort

<dd>
<p>Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-closeport.md">ClosePort</a> function.</p>
</dd>

### -field pfnAddPort

<dd>
<p>(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="print.addport">AddPort</a> function.</p>
</dd>

### -field pfnAddPortEx

<dd>
<p>(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="print.addportex">AddPortEx</a> function. (Port monitors only.)</p>
</dd>

### -field pfnConfigurePort

<dd>
<p>(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="print.configureport">ConfigurePort</a> function.</p>
</dd>

### -field pfnDeletePort

<dd>
<p>(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="print.deleteport">DeletePort</a> function.</p>
</dd>

### -field pfnGetPrinterDataFromPort

<dd>
<p>Pointer to the print monitor's <a href="print.getprinterdatafromport">GetPrinterDataFromPort</a> function.</p>
</dd>

### -field pfnSetPortTimeOuts

<dd>
<p>Pointer to the print monitor's <a href="print.setporttimeouts">SetPortTimeOuts</a> function. (Port monitors only.)</p>
</dd>

### -field pfnXcvOpenPort

<dd>
<p>Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a> function. (Port monitors only.)</p>
</dd>

### -field pfnXcvDataPort

<dd>
<p>Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-xcvdataport.md">XcvDataPort</a> function. (Port monitors only.)</p>
</dd>

### -field pfnXcvClosePort

<dd>
<p>Pointer to the print monitor's <a href="..\winsplp\nf-winsplp-xcvcloseport.md">XcvClosePort</a> function. (Port monitors only.)</p>
</dd>

### -field pfnShutdown

<dd>
<p>Pointer to the print monitor's <a href="print.shutdown">Shutdown</a> function.</p>
</dd>

### -field pfnSendRecvBidiDataFromPort

<dd>
<p>Pointer to the print monitor's <a href="print.sendrecvbididatafromport">SendRecvBidiDataFromPort</a> function.</p>
</dd>
</dl>

## -remarks
<p>Each language monitor and each port monitor server DLL must provide a MONITOR2 structure. The monitor must supply values for all structure members, and specify the structure's address as the return value for its <a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a> function.</p>

<p>If a function is not defined, its pointer must be <b>NULL</b>.</p>

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
<a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a>
</dt>
<dt>
<a href="..\winsplp\ns-winsplp--monitorui.md">MONITORUI</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MONITOR2 structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
