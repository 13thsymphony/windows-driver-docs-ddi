---
UID: NF:winsplp.AddPrintDeviceObject
title: AddPrintDeviceObject function
author: windows-driver-content
description: The AddPrintDeviceObject print provider function creates a device object for a print provider queue.
old-location: print\addprintdeviceobject.htm
old-project: print
ms.assetid: C01071FD-7D1D-4D6F-AFDD-355FFDA699EA
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: AddPrintDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winspool.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AddPrintDeviceObject
req.alt-loc: WinSpool.drv
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WinSpool.lib
req.dll: WinSpool.drv
req.irql: 
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# AddPrintDeviceObject function



## -description

## -syntax

````
HRESULT WINAPI AddPrintDeviceObject(
  _In_  HANDLE hPrinter,
  _Out_ HANDLE *phDeviceObject
);
````


## -parameters

### -param hPrinter [in]

A HANDLE to an open printer. This should be a HANDLE returned by the <b>AddPrinter</b> or <b>OpenPrinter</b> spooler functions.


### -param phDeviceObject [out]

A HANDLE to the device object, if it was created successfully.


## -returns
The <b>AddPrintDeviceObject</b> function returns S_OK, if the device object was created successfully.
    Otherwise it returns an error.


## -remarks
The <b>AddPrintDeviceObject</b> function should be called in the following situations:

<b>User installs a Printer</b>

The print provider should call this function after installing the printer.

The function must be called by impersonating the user who is installing the printer.

<b>Print Provider is intialized after spooler service starts</b>

The print provider should call this function for each previously-installed Printer owned by the provider. During this time, <b>AddPrintDeviceObject</b> doesn't have to impersonate the user context when it is called.<div class="alert"><b>Note</b>  Any device object that is added using  <b>AddPrintDeviceObject</b> will persist until you remove it using <a href="..\winsplp\nf-winsplp-removeprintdeviceobject.md">RemovePrintDeviceObject</a>, or 
    until the spooler service restarts. And when the spooler services stops, all the device objects are automatically deleted.</div>
<div> </div>



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
<dt>Winsplp.h (include Winspool.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>WinSpool.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WinSpool.drv</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\winsplp\nf-winsplp-removeprintdeviceobject.md">RemovePrintDeviceObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20AddPrintDeviceObject function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

