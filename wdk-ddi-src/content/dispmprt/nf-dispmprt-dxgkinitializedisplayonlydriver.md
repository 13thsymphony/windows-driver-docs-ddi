---
UID: NF.dispmprt.DxgkInitializeDisplayOnlyDriver
title: DxgkInitializeDisplayOnlyDriver
author: windows-driver-content
description: Loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys) for use by a kernel mode display-only driver (KMDOD).
old-location: display\dxgkinitializedisplayonlydriver.htm
old-project: display
ms.assetid: d80d2d6a-758f-4b11-b33c-4b176a458bd2
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DxgkInitializeDisplayOnlyDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkInitializeDisplayOnlyDriver
req.alt-loc: Displib.lib,Displib.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Displib.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# DxgkInitializeDisplayOnlyDriver function



## -description
<p>Loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys) for use by a kernel mode display-only driver (KMDOD).</p>


## -syntax

````
NTSTATUS DxgkInitializeDisplayOnlyDriver(
  _In_ PDRIVER_OBJECT              DriverObject,
  _In_ PUNICODE_STRING             RegistryPath,
  _In_ PKMDDOD_INITIALIZATION_DATA KmdDodInitializationData
);
````


## -parameters
<dl>

### -param <i>DriverObject</i> [in]

<dd>
<p>A pointer to a <a href="..\wdm\ns-wdm--driver-object.md">DRIVER_OBJECT</a> structure. The KMDOD previously obtained this pointer in its <a href="display.driverentry_of_display_miniport_driver">DriverEntry</a> function.</p>
</dd>

### -param <i>RegistryPath</i> [in]

<dd>
<p>A pointer to a <a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a> structure that supplies the path to the KMDOD's service registry key.  The KMDOD previously obtained this pointer in its <a href="display.driverentry_of_display_miniport_driver">DriverEntry</a> function.</p>
</dd>

### -param <i>KmdDodInitializationData</i> [in]

<dd>
<p>A pointer to a <a href="..\dispmprt\ns-dispmprt--kmddod-initialization-data.md">KMDDOD_INITIALIZATION_DATA</a> structure that supplies the DirectX graphics kernel subsystem with pointers to functions implemented by the KMDOD.</p>
</dd>
</dl>

## -returns
<p>
      Returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.</p>

## -remarks
<p>All parameters that are supplied by the KMDOD can be in paged memory.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
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
<dt>Dispmprt.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Displib.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.driverentry_of_display_miniport_driver">DriverEntry of Display Miniport Driver</a>
</dt>
<dt>
<a href="..\dispmprt\ns-dispmprt--kmddod-initialization-data.md">KMDDOD_INITIALIZATION_DATA</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--driver-object.md">DRIVER_OBJECT</a>
</dt>
<dt>
<a href="..\dispmprt\nf-dispmprt-dxgkinitialize.md">DxgkInitialize</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DxgkInitializeDisplayOnlyDriver function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
