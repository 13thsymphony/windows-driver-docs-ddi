---
UID: NF.winsplp.XcvDataPort
title: XcvDataPort function
author: windows-driver-content
description: A port monitor server DLL's XcvDataPort function receives information from, and returns information to, the port monitor's UI DLL.
old-location: print\xcvdataport.htm
old-project: print
ms.assetid: 2d0e3509-27d9-439f-9d47-e0e500e8907f
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: XcvDataPort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: XcvDataPort
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

# XcvDataPort function



## -description
A port monitor server DLL's <b>XcvDataPort</b> function receives information from, and returns information to, the port monitor's UI DLL.


## -syntax

````
DWORD XcvDataPort(
  _In_  HANDLE  hXcv,
  _In_  LPCWSTR pszDataName,
  _In_  PBYTE   pInputData,
        DWORD   cbInputData,
  _Out_ PBYTE   pOutputData,
        DWORD   cbOutputData,
  _Out_ PDWORD  pcbOutputNeeded
);
````


## -parameters

### -param hXcv [in]

Caller-supplied printer handle, obtained by calling <b>OpenPrinter</b> (described in the Microsoft Windows SDK documentation). This handle is created and returned by the <a href="print.xcvopenport">XcvOpenPort</a> function.

### -param pszDataName [in]

Caller-supplied pointer to a string representing the name of the data being requested. For more information, see the following Remarks section.

### -param pInputData [in]

Caller-supplied pointer to a buffer containing input data.

### -param cbInputData 

Caller-supplied size, in bytes, of the buffer pointed to by <i>pInputData</i>.

### -param pOutputData [out]

Caller-supplied pointer to a buffer to receive output data.

### -param cbOutputData 

Caller-supplied size, in bytes, of the buffer pointed to by <i>pOutputData</i>.

### -param pcbOutputNeeded [out]

Caller-supplied pointer to a location to receive the minimum size, in bytes, required for the buffer pointed to by <i>pOutputData</i>.

## -returns
If the operation succeeds, this function should return ERROR_SUCCESS. Otherwise, it should return an ERROR_-prefixed Win32 error code. The print monitor UI DLL receives this value in the <i>pdwStatus</i> location specified for <a href="print.xcvdata">XcvData</a>.

## -remarks
Port monitor server DLLs are required to define an <b>XcvDataPort</b> function so they can receive information from, and return information to, a port monitor UI DLL. The function's address must be included in a <a href="print.monitor2">MONITOR2</a> structure.

The <b>XcvDataPort</b> function is called by the spooler's <a href="print.xcvdata">XcvData</a> function. The function parameters for <b>XcvDataPort</b> and <b>XcvData</b> are almost identical. (<b>XcvData</b> has an additional parameter, <i>pdwStatus</i>, that is not present in <b>XcvDataPort</b>.)

The string pointed to by <i>pszDataName</i> specifies the operation to be performed. The function must recognize the following data name strings:

L"AddPort"

All information needed for adding a port has been sent. The function should perform operations necessary to add the specified port, including writing the port name in the registry under the Ports key.

The <i>pInputData</i> parameter points to a NULL-terminated port name string.

If the function returns ERROR_SUCCESS, the spooler marks the port as added.

This string is specified by the print monitor UI DLL, from within its <a href="print.addportui">AddPortUI</a> function.

L"DeletePort"

All information needed for deleting a port has been sent. The function should perform operations necessary to delete the specified port, including removing the port name from the registry's Ports key.

If the function returns ERROR_SUCCESS, the spooler marks the port as deleted.

This string is specified by the print monitor UI DLL, from within its <a href="print.deleteportui">DeletePortUI</a> function.

L"MonitorUI"

The function should use <i>pOutputData</i> to return the name of the associated port monitor UI DLL.

This string is specified by the print spooler, when an application calls the Microsoft Windows SDK <b>AddPort</b> function.

Typically, the function is written to recognize additional, customized strings that are sent by the UI DLL from within its <a href="print.addportui">AddPortUI</a>, <a href="print.configureportui">ConfigurePortUI</a>, and <a href="print.deleteportui">DeletePortUI</a> functions. These strings might represent commands that request current configuration values from the server DLL, or that deliver new values. For example, your <b>XcvDataPort</b> function might recognize the string "GetTransmissionRetryTimeout", which your UI DLL could send to your server DLL to request the currently stored transmission retry time-out value. Or, you might define a set of strings that must be sent before "AddPort" or "DeletePort" is sent, where the strings are used to supply information identifying the port to add or delete.

For a given <i>pszDataName</i> string and input buffer, <b>XcvDataPort</b> might first be called with a <i>cbOutputData</i> value of zero. The function should return a required buffer size in <i>pcbOutputNeeded</i>, along with a return value of ERROR_INSUFFICIENT_BUFFER. The caller can use the value received in <i>pcbOutputNeeded</i> to allocate an output buffer of adequate size, and can then call <b>XcvDataPort</b> again, this time specifying the allocated buffer size in <i>cbOutputData</i>.

The <b>XcvDataPort</b> function must validate all input arguments. Specifically, the function must:

Validate the contents of the string pointed to by the <i>pszDataName</i> parameter. If this string represents an administrative operation (typically adding, deleting, or configuring a port), the <b>XcvDataPort</b> function should compare the granted access mask that was previously received by the <a href="print.xcvopenport">XcvOpenPort</a> function with SERVER_ACCESS_ADMINISTER. If the comparison fails, <b>XcvDataPort</b> must  return ERROR_ACCESS_DENIED. 

Validate the contents of the buffer pointed to by the <i>pInputData</i> parameter. When the spooler calls the <b>XcvOpenPort</b> function, it performs no validation on the contents of this buffer. The monitor can make no assumptions about the validity of this data, which can come from a malicious application.

If you are writing a port monitor that will communicate with TCPMON, see <a href="https://msdn.microsoft.com/7b2b1cff-ab8f-44e0-9327-dc60a0072bf5">TCPMON Xcv Interface</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<a href="print.xcvopenport">XcvOpenPort</a>
</dt>
<dt>
<a href="print.xcvdata">XcvData</a>
</dt>
<dt>
<a href="print.addportui">AddPortUI</a>
</dt>
<dt>
<a href="print.configureportui">ConfigurePortUI</a>
</dt>
<dt>
<a href="print.deleteportui">DeletePortUI</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20XcvDataPort function%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
