---
UID: NS.WDFDPC._WDF_DPC_CONFIG
title: _WDF_DPC_CONFIG
author: windows-driver-content
description: The WDF_DPC_CONFIG structure contains configuration information for a DPC object.
old-location: wdf\wdf_dpc_config.htm
old-project: wdf
ms.assetid: e4203a9d-98f4-47f2-80ea-51074e4c0713
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_DPC_CONFIG, *PWDF_DPC_CONFIG, WDF_DPC_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdpc.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WDF_DPC_CONFIG
req.alt-loc: wdfdpc.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.product: Windows 10 or later.
---

# _WDF_DPC_CONFIG structure



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DPC_CONFIG</b> structure contains configuration information for a DPC object.



## -syntax

````
typedef struct _WDF_DPC_CONFIG {
  ULONG       Size;
  PFN_WDF_DPC EvtDpcFunc;
  BOOLEAN     AutomaticSerialization;
} WDF_DPC_CONFIG, *PWDF_DPC_CONFIG;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field EvtDpcFunc

A pointer to the driver's <a href="wdf.evtdpcfunc">EvtDpcFunc</a> callback function.


### -field AutomaticSerialization

A Boolean value that, if <b>TRUE</b>, indicates that the framework will synchronize execution of the DPC object's <a href="wdf.evtdpcfunc">EvtDpcFunc</a> callback function with callback functions from other objects that are underneath the DPC object's parent. For more information, see the following Remarks section.


## -remarks
The <b>WDF_DPC_CONFIG</b> structure is used as input to <a href="wdf.wdfdpccreate">WdfDpcCreate</a>. 

To initialize a <b>WDF_DPC_CONFIG</b> structure, your driver should first call <a href="wdf.wdf_dpc_config_init">WDF_DPC_CONFIG_INIT</a> and then fill in structure members that <b>WDF_DPC_CONFIG_INIT</b> does not initialize.

Setting <b>AutomaticSerialization</b> to <b>TRUE</b> has no effect if the parent device object's <a href="wdf.wdf_synchronization_scope">synchronization scope</a> is set to <b>WdfSynchronizationScopeNone</b>.

Setting <b>AutomaticSerialization</b> to <b>TRUE</b> causes <a href="wdf.wdfdpccreate">WdfDpcCreate</a> to fail if the parent device object's <a href="wdf.wdf_execution_level">execution level</a> is set to <b>WdfExecutionLevelPassive</b>.

For more information about <b>AutomaticSerialization</b> and synchronizing driver callback functions, see <a href="wdf.synchronization_techniques_for_wdf_drivers">Synchronization Techniques for Framework-Based Drivers</a>.

For more information about handling interrupts in framework-based drivers, see <a href="wdf.handling_hardware_interrupts">Handling Hardware Interrupts</a>.


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdpc.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfdpccreate">WdfDpcCreate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>
</dt>
<dt>
<a href="wdf.wdf_dpc_config_init">WDF_DPC_CONFIG_INIT</a>
</dt>
<dt>
<a href="wdf.evtdpcfunc">EvtDpcFunc</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DPC_CONFIG structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

