---
UID: NF.wdfqueryinterface.WDF_QUERY_INTERFACE_CONFIG_INIT
title: WDF_QUERY_INTERFACE_CONFIG_INIT function
author: windows-driver-content
description: The WDF_QUERY_INTERFACE_CONFIG_INIT function initializes a driver's WDF_QUERY_INTERFACE_CONFIG structure.
old-location: wdf\wdf_query_interface_config_init.htm
old-project: wdf
ms.assetid: 509f4fa5-37c8-4098-aade-767aad5d6d6a
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WDF_QUERY_INTERFACE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfqueryinterface.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WDF_QUERY_INTERFACE_CONFIG_INIT
req.alt-loc: Wdfqueryinterface.h
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

# WDF_QUERY_INTERFACE_CONFIG_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_QUERY_INTERFACE_CONFIG_INIT</b> function initializes a driver's <a href="wdf.wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure.



## -syntax

````
VOID WDF_QUERY_INTERFACE_CONFIG_INIT(
  _Out_          PWDF_QUERY_INTERFACE_CONFIG                    InterfaceConfig,
  _In_           PINTERFACE                                     Interface,
  _In_     const GUID                                           *InterfaceType,
  _In_opt_       PFN_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST EvtDeviceProcessQueryInterfaceRequest
);
````


## -parameters

### -param InterfaceConfig [out]

A pointer to the driver's <a href="wdf.wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure.


### -param Interface [in]

A pointer to an <a href="kernel.interface">INTERFACE</a> structure.


### -param InterfaceType [in]

A pointer to the GUID that identifies the interface.


### -param EvtDeviceProcessQueryInterfaceRequest [in, optional]

A pointer to the driver's <a href="wdf.evtdeviceprocessqueryinterfacerequest">EvtDeviceProcessQueryInterfaceRequest</a> event callback function, which is called when another driver requests the interface.


## -returns
None


## -remarks
For more information about driver-defined interfaces, see <a href="wdf.using_driver_defined_interfaces">Using Driver-Defined Interfaces</a>.

For a code example that uses <b>WDF_QUERY_INTERFACE_CONFIG_INIT</b>, see <a href="wdf.wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
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
<dt>Wdfqueryinterface.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.evtdeviceprocessqueryinterfacerequest">EvtDeviceProcessQueryInterfaceRequest</a>
</dt>
<dt>
<a href="kernel.interface">INTERFACE</a>
</dt>
<dt>
<a href="wdf.wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_QUERY_INTERFACE_CONFIG_INIT function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

