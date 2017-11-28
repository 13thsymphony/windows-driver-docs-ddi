---
UID: NF.wdffdo.WdfFdoUnlockStaticChildListFromIteration
title: WdfFdoUnlockStaticChildListFromIteration
author: windows-driver-content
description: The WdfFdoUnlockStaticChildListFromIteration method unlocks the list of child devices for a specified device and processes any changes to the list that the driver made while the list was locked.
old-location: wdf\wdffdounlockstaticchildlistfromiteration.htm
old-project: wdf
ms.assetid: ba0eb090-a03c-4723-a30c-16b161e50198
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WdfFdoUnlockStaticChildListFromIteration
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfFdoUnlockStaticChildListFromIteration
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WdfFdoUnlockStaticChildListFromIteration function



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>The <b>WdfFdoUnlockStaticChildListFromIteration</b> method unlocks the list of child devices for a specified device and processes any changes to the list that the driver made while the list was locked. </p>


## -syntax

````
VOID WdfFdoUnlockStaticChildListFromIteration(
  _In_ WDFDEVICE Fdo
);
````


## -parameters
<dl>

### -param <i>Fdo</i> [in]

<dd>
<p>A handle to a framework device object that represents the parent device.</p>
</dd>
</dl>

## -returns
<p>None.</p>

<p>A system bug check occurs if the driver supplies an invalid object handle.</p>

## -remarks
<p>Bus drivers that use static bus enumeration can call <b>WdfFdoUnlockStaticChildListFromIteration</b>. </p>

<p>To lock a child list, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a>. </p>

<p>Calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a> can be nested and must be matched by an equal number of calls to <b>WdfFdoUnlockStaticChildListFromIteration</b>. If a driver adds or removes items from the child list while it is locked, the framework queues these changes and processes them after the last call to <b>WdfFdoUnlockStaticChildListFromIteration</b>.</p>

<p>For more information about static child lists, see <a href="wdf.enumerating_the_devices_on_a_bus">Enumerating the Devices on a Bus</a>.</p>

<p>For a code example that uses <b>WdfFdoUnlockStaticChildListFromIteration</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547293">WdfFdoRetrieveNextStaticChild</a>.</p>

<p>Bus drivers that use static bus enumeration can call <b>WdfFdoUnlockStaticChildListFromIteration</b>. </p>

<p>To lock a child list, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a>. </p>

<p>Calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a> can be nested and must be matched by an equal number of calls to <b>WdfFdoUnlockStaticChildListFromIteration</b>. If a driver adds or removes items from the child list while it is locked, the framework queues these changes and processes them after the last call to <b>WdfFdoUnlockStaticChildListFromIteration</b>.</p>

<p>For more information about static child lists, see <a href="wdf.enumerating_the_devices_on_a_bus">Enumerating the Devices on a Bus</a>.</p>

<p>For a code example that uses <b>WdfFdoUnlockStaticChildListFromIteration</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547293">WdfFdoRetrieveNextStaticChild</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdffdo.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoUnlockStaticChildListFromIteration method%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
