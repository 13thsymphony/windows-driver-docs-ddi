---
UID: NF.dbgeng.IDebugControl4.GetSystemVersionStringWide
title: IDebugControl4::GetSystemVersionStringWide method
author: windows-driver-content
description: The GetSystemVersionStringWide method returns a string that describes the target's operating system version.
old-location: debugger\getsystemversionstringwide.htm
old-project: Debugger
ms.assetid: a98dee8a-1911-40e0-b1fd-c7a1ee40a8d7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugControl4, IDebugControl4::GetSystemVersionStringWide, GetSystemVersionStringWide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl4.GetSystemVersionStringWide
req.alt-loc: dbgeng.h
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
---

# IDebugControl4::GetSystemVersionStringWide method



## -description
The <b>GetSystemVersionStringWide</b>  method returns a string that describes the target's operating system version.



## -syntax

````
HRESULT GetSystemVersionStringWide(
  [in]            ULONG  Which,
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG StringSize
);
````


## -parameters

### -param Which [in]

Specifies which version string to return.  The possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Version string</th>
</tr>
<tr>
<td>
DEBUG_SYSVERSTR_SERVICE_PACK

</td>
<td>
Returns a description of the service pack for the target's operating system.  For example, "Service Pack 1".

</td>
</tr>
<tr>
<td>
DEBUG_SYSVERSTR_BUILD

</td>
<td>
Returns a description of the target's operating system build version.  For example, "kernel32.dll version: 5.1.2600.1106 (xpsp1.020828-1920)".

</td>
</tr>
</table>
 


### -param Buffer [out, optional]

Receives the version string.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param StringSize [out, optional]

Receives the size, in characters, of the string that identifies the build.  If <i>SizeString</i> is <b>NULL</b>, this information is not returned.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful. However, the buffer was too small, so the string was truncated.

 


## -remarks
For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.


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
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="debugger.getsystemversion">GetSystemVersion</a>
</dt>
<dt>
<a href="debugger.getsystemversionvalues">GetSystemVersionValues</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl4::GetSystemVersionStringWide method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

