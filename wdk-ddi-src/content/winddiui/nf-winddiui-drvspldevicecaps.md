---
UID: NF.winddiui.DrvSplDeviceCaps
title: DrvSplDeviceCaps
author: windows-driver-content
description: A printer interface DLL's DrvSplDeviceCaps function queries a printer for its capabilities.
old-location: print\drvspldevicecaps.htm
old-project: print
ms.assetid: 3d129a30-a892-4f4d-b8e3-f277d97980f4
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: DrvSplDeviceCaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winddiui.h
req.include-header: Winddiui.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DrvSplDeviceCaps
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
req.iface: 
req.product: Windows 10 or later.
---

# DrvSplDeviceCaps function



## -description
<p>A printer interface DLL's <b>DrvSplDeviceCaps</b> function queries a printer for its capabilities.</p>


## -syntax

````
DWORD DrvSplDeviceCaps(
            HANDLE   hPrinter,
  _In_      PWSTR    pwDeviceName,
            WORD     DeviceCap,
  _Out_opt_ PVOID    pvOutput,
            DWORD    cchBuf,
  _In_opt_  PDEVMODE pDM
);
````


## -parameters
<dl>

### -param <i>hPrinter</i> 

<dd>
<p>Caller-supplied handle to the printer.</p>
</dd>

### -param <i>pwDeviceName</i> [in]

<dd>
<p>Caller-supplied pointer to a Unicode string that contains the printer name.</p>
</dd>

### -param <i>DeviceCap</i> 

<dd>
<p>Caller-supplied bit flag that indicates the capability to query for. (The flags are defined in header file wingdi.h.) This function is not required to support all of the DC_<i>XXX</i> flags, but it must support those listed in the following table.</p>
<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
<p>DC_MEDIAREADY</p>
</td>
<td>
<p>The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each array element should contain a NULL-terminated string representing a name for a paper form that is available for use. </p>
<p>The function's return value should be the number of elements in the returned array.</p>
<p>If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.</p>
</td>
</tr>
<tr>
<td>
<p>DC_PAPERNAMES</p>
</td>
<td>
<p>The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each array element should contain a NULL-terminated string representing a name for a paper form. </p>
<p>The function's return value should be the number of elements in the returned array.</p>
<p>If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>pvOutput</i> [out, optional]

<dd>
<p>Caller-supplied pointer to a buffer that receives function-supplied information. The buffer's use depends on the value of  the <i>DeviceCap</i> parameter. The caller is responsible for allocating and freeing this buffer. </p>
</dd>

### -param <i>cchBuf</i> 

<dd>
<p>Caller-supplied size (in characters) of the buffer pointed to by the <i>pvOutput</i> parameter.</p>
</dd>

### -param <i>pDM</i> [in, optional]

<dd>
<p>Caller-supplied pointer to a <a href="display.devmodew">DEVMODEW</a> structure that describes the current print job characteristics. If <b>NULL</b>, the function should use the driver's internal default DEVMODEW structure. </p>
</dd>
</dl>

## -returns
<p>The return value depends on the <i>DeviceCap</i> parameter. If <i>DeviceCap</i> indicates a capability that the driver does not support, or if an error is encountered, the function should return GDI_ERROR.</p>

## -remarks
<p>The <b>DrvSplDeviceCaps</b> function is available in Microsoft Windows Server 2003 and later.</p>

<p>For descriptions of the DC_<i>XXX</i> flags, see <a href="..\winddiui\nf-winddiui-drvdevicecapabilities.md">DrvDeviceCapabilities</a>.</p>

<p>This function must be defined in the .def file as DrvSplDeviceCaps @ 254, because the spooler uses the ordinal number 254 to obtain the driver function pointer.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\winddiui\nf-winddiui-drvdevicecapabilities.md">DrvDeviceCapabilities</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DrvSplDeviceCaps function%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
