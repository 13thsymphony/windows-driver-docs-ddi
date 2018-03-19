---
UID: NS:winsplp._MONITORREG
title: "_MONITORREG"
author: windows-driver-content
description: The MONITORREG structure supplies print monitors with the address of registry functions to use instead of Win32 registry API functions.
old-location: print\monitorreg.htm
old-project: print
ms.assetid: 57c146bc-574f-4137-89bb-e891e005de05
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMONITORREG, MONITORREG, MONITORREG structure [Print Devices], PMONITORREG, PMONITORREG structure pointer [Print Devices], _MONITORREG, print.monitorreg, spoolfnc_2d0db8db-eea5-461a-a257-1fb986001dac.xml, winsplp/MONITORREG, winsplp/PMONITORREG"
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
-	winsplp.h
api_name:
-	MONITORREG
product: Windows
targetos: Windows
req.typenames: MONITORREG, *PMONITORREG
req.product: Windows 10 or later.
---

# _MONITORREG structure
The MONITORREG structure supplies print monitors with the address of registry functions to use instead of Win32 registry API functions.

## Syntax
````
typedef struct _MONITORREG {
  DWORD cbSize;
  LONG  (WINAPI *fpCreateKey)(
      HKEYMONITOR hcKey, 
      LPCTSTR pszSubKey, 
      DWORD dwOptions, 
      REGSAM samDesired, 
      PSECURITY_ATTRIBUTES pSecurityAttributes, 
      HKEYMONITOR phckResult, 
      PDWORD pdwDisposition, 
      HANDLE hSpooler);
  LONG  (WINAPI *fpOpenKey)(
      HKEYMONITOR hcKey, 
      LPCTSTR pszSubKey, 
      REGSAM samDesired, 
      HKEYMONITOR phkResult, 
      HANDLE hSpooler);
  LONG  (WINAPI *fpCloseKey)(
      HKEYMONITOR hcKey, 
      HANDLE hSpooler);
  LONG  (WINAPI *fpDeleteKey)(
      HKEYMONITOR hcKey, 
      LPCTSTR pszSubKey, 
      HANDLE hSpooler);
  LONG  (WINAPI *fpEnumKey)(
      HKEYMONITOR hcKey, 
      DWORD dwIndex, 
      LPTSTR pszName, 
      PDWORD pcchName, 
      PFILETIME pftLastWriteTime, 
      HANDLE hSpooler);
  LONG  (WINAPI *fpQueryInfoKey)(
      HKEYMONITOR hcKey, 
      PDWORD pcSubKeys, 
      PDWORD pcbKey, 
      PDWORD pcValues, 
      PDWORD pcbValue, 
      PDWORD pcbData, 
      PDWORD pcbSecurityDescriptor, 
      PFILETIME pftLastWriteTime, 
      HANDLE hSpooler);
  LONG  (WINAPI *fpSetValue)(
      HKEYMONITOR hcKey, 
      LPCTSTR pszValue, 
      DWORD dwType, 
      const BYTE* pData, 
      DWORD cbData, 
      HANDLE hSpooler);
  LONG  (WINAPI *fpDeleteValue)(
      HKEYMONITOR hcKey, 
      LPCTSTR pszValue, 
      HANDLE hSpooler);
  LONG  (WINAPI *fpEnumValue)(
      HKEYMONITOR hcKey, 
      DWORD dwIndex, 
      LPTSTR pszValue, 
      PDWORD pcbValue, 
      PDWORD pTyp, 
      PBYTE pcbData, 
      PDWORD pcbData, 
      HANDLE hSpooler);
  LONG  (WINAPI *fpQueryValue)(
      HKEYMONITOR hcKey, 
      LPCTSTR pszValue, 
      PDWORD pType, 
      PBYTE pData, 
      PDWORD pcbData, 
      HANDLE hSpooler);
} MONITORREG, *PMONITORREG;
````

## Members


`cbSize`

Size, in bytes, of the MONITORREG structure.

`fpCreateKey`



`fpOpenKey`



`fpCloseKey`



`fpDeleteKey`



`fpEnumKey`



`fpQueryInfoKey`



`fpSetValue`



`fpDeleteValue`



`fpEnumValue`



`fpQueryValue`



## Remarks
The MONITORREG structure's address is supplied in a <a href="..\winsplp\ns-winsplp-_monitorinit.md">MONITORINIT</a> structure, which is passed to a print monitor's <a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a> function.

When <a href="https://msdn.microsoft.com/b1c83729-d7d2-4920-9402-4e00baa12633">storing port configuration information</a>, print monitors must not explicitly call either the Win32 registry API or the cluster registry API. Instead, they must call equivalent spooler registry functions. The MONITORREG structure supplies the addresses of these functions. The following table lists each spooler registry function and its equivalent cluster registry function.

<table>
<tr>
<th>Spooler Registry Function</th>
<th>Equivalent Cluster Registry Function</th>
</tr>
<tr>
<td>
<b>CreateKey</b>

</td>
<td>
<b>ClusterRegCreateKey</b>

</td>
</tr>
<tr>
<td>
<b>OpenKey</b>

</td>
<td>
<b>ClusterRegOpenKey</b>

</td>
</tr>
<tr>
<td>
<b>CloseKey</b>

</td>
<td>
<b>ClusterRegCloseKey</b>

</td>
</tr>
<tr>
<td>
<b>DeleteKey</b>

</td>
<td>
<b>ClusterRegDeleteKey</b>

</td>
</tr>
<tr>
<td>
<b>EnumKey</b>

</td>
<td>
<b>ClusterRegEnumKey</b>

</td>
</tr>
<tr>
<td>
<b>QueryInfoKey</b>

</td>
<td>
<b>ClusterRegQueryInfoKey</b>

</td>
</tr>
<tr>
<td>
<b>SetValue</b>

</td>
<td>
<b>ClusterRegSetValue</b>

</td>
</tr>
<tr>
<td>
<b>DeleteValue</b>

</td>
<td>
<b>ClusterRegDeleteValue</b>

</td>
</tr>
<tr>
<td>
<b>EnumValue</b>

</td>
<td>
<b>ClusterRegEnumValue</b>

</td>
</tr>
<tr>
<td>
<b>QueryValue</b>

</td>
<td>
<b>ClusterRegQueryValue</b>

</td>
</tr>
</table>
 

Input and output parameters for these spooler functions match the parameters of the equivalent cluster registry functions (described in the Microsoft Windows SDK documentation), with the following exceptions:

<ul>
<li>
Each spooler registry function requires an <i>hSpooler</i> input parameter. This is the spooler handle received in the <a href="..\winsplp\ns-winsplp-_monitorinit.md">MONITORINIT</a> structure.

</li>
<li>
The spooler registry functions use HANDLE and PHANDLE parameter types instead of the HKEY and PHKEY types used by the cluster registry functions. Monitors receive the handle of the root registry location in the <b>hckRegistryRoot</b> member of the <a href="..\winsplp\ns-winsplp-_monitorinit.md">MONITORINIT</a> structure.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winsplp.h (include Winsplp.h) |

## See Also

<a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a>



<a href="..\winsplp\ns-winsplp-_monitorinit.md">MONITORINIT</a>