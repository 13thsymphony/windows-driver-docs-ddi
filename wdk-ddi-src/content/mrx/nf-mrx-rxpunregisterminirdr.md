---
UID: NF.mrx.RxpUnregisterMinirdr
title: RxpUnregisterMinirdr
author: windows-driver-content
description: RxpUnregisterMinirdr is called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.
old-location: ifsk\rxpunregisterminirdr.htm
old-project: ifsk
ms.assetid: 84155e3f-8090-4b0d-a101-25ecd126bc37
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RxpUnregisterMinirdr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxpUnregisterMinirdr
req.alt-loc: mrx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.iface: 
---

# RxpUnregisterMinirdr function



## -description
<p><b>RxpUnregisterMinirdr</b> is called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.</p>


## -syntax

````
VOID RxpUnregisterMinirdr(
  _In_ PRDBSS_DEVICE_OBJECT RxDeviceObject
);
````


## -parameters
<dl>

### -param <i>RxDeviceObject</i> [in]

<dd>
<p>A pointer to the RDBSS device object for this network redirector.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The <b>RxpUnregisterMinirdr</b> routine unregisters the driver with RDBSS and removes the registration information from the internal RDBSS registration table. If name tables were initialized, then these tables will be finalized for release. Any outstanding asynchronous requests to the network mini-redirector are spun down, and any worker threads associated with the redirector are spun down. <b>RxpUnregisterMinirdr</b> also tries to remove the device object from the system by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549083">IoDeleteDevice</a>.</p>

<p>The <b>RxpUnregisterMinirdr </b>routine is usually called as a result of an FSCTL or IOCTL request from a user-mode application or service to unload the network mini-redirector, although this call could also be made from the network mini-redirector or as part of shutdown processing by the operating system or as a result of a failure in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. </p>

<p>Note that the inline routine, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554744">RxUnregisterMinirdr</a>, is the preferred way to unregister a driver with RDBSS. The <b>RxUnregisterMinirdr</b> inline routine calls <b>RxpUnregisterMinirdr</b>, but then also decrements the object reference to the RDBSS device object so that this object can be released by the system. </p>

<p>The <b>RxpUnregisterMinirdr</b> routine unregisters the driver with RDBSS and removes the registration information from the internal RDBSS registration table. If name tables were initialized, then these tables will be finalized for release. Any outstanding asynchronous requests to the network mini-redirector are spun down, and any worker threads associated with the redirector are spun down. <b>RxpUnregisterMinirdr</b> also tries to remove the device object from the system by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549083">IoDeleteDevice</a>.</p>

<p>The <b>RxpUnregisterMinirdr </b>routine is usually called as a result of an FSCTL or IOCTL request from a user-mode application or service to unload the network mini-redirector, although this call could also be made from the network mini-redirector or as part of shutdown processing by the operating system or as a result of a failure in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. </p>

<p>Note that the inline routine, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554744">RxUnregisterMinirdr</a>, is the preferred way to unregister a driver with RDBSS. The <b>RxUnregisterMinirdr</b> inline routine calls <b>RxpUnregisterMinirdr</b>, but then also decrements the object reference to the RDBSS device object so that this object can be released by the system. </p>

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
<dt>Mrx.h (include Mrx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549083">IoDeleteDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554693">RxRegisterMinirdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554736">RxStartMiniRdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554743">RxStopMiniRdr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554744">RxUnregisterMinirdr</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxpUnregisterMinirdr function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
