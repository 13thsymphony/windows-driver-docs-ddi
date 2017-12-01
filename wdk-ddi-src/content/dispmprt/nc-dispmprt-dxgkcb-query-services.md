---
UID: NC.dispmprt.DXGKCB_QUERY_SERVICES
title: DXGKCB_QUERY_SERVICES
author: windows-driver-content
description: The DxgkCbQueryServices function returns an interface implemented by the display port driver.
old-location: display\dxgkcbqueryservices.htm
old-project: display
ms.assetid: 0ce5df90-2019-4a92-97d6-0218acc8b1e8
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbQueryServices
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: IDebugSystemObjects4
---

# DXGKCB_QUERY_SERVICES callback



## -description
<p>The <b>DxgkCbQueryServices</b> function returns an interface implemented by the display port driver.</p>


## -prototype

````
DXGKCB_QUERY_SERVICES DxgkCbQueryServices;

NTSTATUS DxgkCbQueryServices(
  _In_    HANDLE        DeviceHandle,
  _In_    DXGK_SERVICES ServicesType,
  _Inout_ PINTERFACE    Interface
)
{ ... }
````


## -parameters
<dl>

### -param <i>DeviceHandle</i> [in]

<dd>
<p>A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="display.dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a>.</p>
</dd>

### -param <i>ServicesType</i> [in]

<dd>
<p>A constant from the <a href="..\dispmprt\ne-dispmprt-dxgk-services.md">DXGK_SERVICES</a> enumeration that specifies which interface is being requested. This parameter must be set to <b>DxgkServicesAgp</b>, <b>DxgkServicesDebugReport</b>, or <b>DxgkServicesTimedOperation</b>, as those are the only supported interfaces.</p>
</dd>

### -param <i>Interface</i> [in, out]

<dd>
<p>A pointer to an <a href="..\wdm\ns-wdm--interface.md">INTERFACE</a> structure that receives the requested interface.</p>
</dd>
</dl>

## -returns
<p><b>DxgkCbQueryServices</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.</p>

## -remarks
<p>An interface, in this context, is a set of functions implemented by the display port driver. The display port driver makes the functions of an interface available to other drivers by providing function pointers in response to <b>DxgkCbQueryServices</b>.</p>

<p>To obtain an AGP interface, do the following:</p>

<p>Allocate a <a href="..\dispmprt\ns-dispmprt--dxgk-agp-interface.md">DXGK_AGP_INTERFACE</a> structure.</p>

<p>Set the <b>Size</b> member to sizeof(DXGK_AGP_INTERFACE).</p>

<p>Set the <b>Version</b> member. Version constants are defined in <i>Dispmprt.h</i> (for example, DXGK_AGP_INTERFACE_VERSION_1).</p>

<p>Call <b>DxgkCbQueryServices</b>; set <i>ServicesType</i> to <b>DxgkServicesAgp</b>, and set <i>Interface</i> to the address (cast as PINTERFACE) of your DXGK_AGP_INTERFACE structure.</p>

<p>On return from <b>DxgkCbQueryServices</b>, your DXGK_AGP_INTERFACE structure will contain pointers to the interface functions: <a href="..\dispmprt\nc-dispmprt-dxgkcb-agp-allocate-pool.md">AgpAllocatePool</a> and the like.</p>

<p>To obtain a Debug Report interface, do the following:</p>

<p>Allocate a <a href="..\dispmprt\ns-dispmprt--dxgk-debug-report-interface.md">DXGK_DEBUG_REPORT_INTERFACE</a> structure.</p>

<p>Set the <b>Size</b> member to sizeof(DXGK_DEBUG_REPORT_INTERFACE).</p>

<p>Set the <b>Version</b> member. Version constants are defined in <i>Dispmprt.h</i> (for example,  DXGK_DEBUG_REPORT_INTERFACE_VERSION_1).</p>

<p>Call <b>DxgkCbQueryServices</b>; set <i>ServicesType</i> to <b>DxgkServicesDebugReport</b>, and set <i>Interface</i> to the address (cast as PINTERFACE) of your DXGK_DEBUG_REPORT_INTERFACE structure.</p>

<p>On return from <b>DxgkCbQueryServices</b>, your DXGK_DEBUG_REPORT_INTERFACE structure will contain pointers to the interface functions: <a href="display.dbgreportcreate2">DbgReportCreate</a> and the like.</p>

<p>To obtain a Timed Operation interface, do the following:</p>

<p>Allocate a <a href="..\dispmprt\ns-dispmprt--dxgk-timed-operation-interface.md">DXGK_TIMED_OPERATION_INTERFACE</a> structure.</p>

<p>Set the <b>Size</b> member to sizeof(DXGK_TIMED_OPERATION_INTERFACE).</p>

<p>Set the <b>Version</b> member. Version constants are defined in <i>Dispmprt.h</i> (for example,  DXGK_TIMED_OPERATION_INTERFACE_VERSION_1).</p>

<p>Call <b>DxgkCbQueryServices</b>; set <i>ServicesType</i> to <b>DxgkServicesTimedOperation</b>, and set <i>Interface</i> to the address (cast as PINTERFACE) of your DXGK_TIMED_OPERATION_INTERFACE structure.</p>

<p>On return from <b>DxgkCbQueryServices</b>, your DXGK_TIMED_OPERATION_INTERFACE structure will contain pointers to the interface functions: <a href="display.timedoperationstart">TimedOperationStart</a> and the like.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
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
<a href="..\wdm\ns-wdm--interface.md">INTERFACE</a>
</dt>
<dt>
<a href="display.agp_interface">AGP Interface</a>
</dt>
<dt>
<a href="display.debug_report_interface">Debug Report Interface</a>
</dt>
<dt>
<a href="display.timed_operation_interface">Timed Operation Interface</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_QUERY_SERVICES callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
