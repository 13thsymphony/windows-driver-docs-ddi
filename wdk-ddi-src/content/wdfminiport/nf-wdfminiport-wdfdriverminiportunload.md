---
UID: NF:wdfminiport.WdfDriverMiniportUnload
title: WdfDriverMiniportUnload function
author: windows-driver-content
description: The WdfDriverMiniportUnload method deletes a specified miniport driver's framework driver object.
old-location: wdf\wdfdriverminiportunload.htm
old-project: wdf
ms.assetid: 57220a12-e53d-482a-afb6-09bfbbf0d870
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDriverMiniportUnload
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfminiport.h
req.include-header: Wdfminiport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDriverMiniportUnload
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: *PWDF_MEMORY_DESCRIPTOR, WDF_MEMORY_DESCRIPTOR
req.product: Windows 10 or later.
---

# WdfDriverMiniportUnload function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDriverMiniportUnload</b> method deletes a specified miniport driver's framework driver object.



## -syntax

````
VOID WdfDriverMiniportUnload(
  _In_ WDFDRIVER Driver
);
````


## -parameters

### -param Driver [in]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> or <a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>.


## -returns
None


## -remarks
A miniport driver calls the <b>WdfDriverMiniportUnload</b> method when the miniport driver is about to be unloaded. The method calls the driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a> event callback function and deletes the driver's framework driver object.

Typically, a miniport driver calls <b>WdfDriverMiniportUnload</b> from within a driver-supplied unload routine that is defined by the port driver's architecture.

For more information about miniport drivers, see <a href="wdf.creating_kmdf_miniport_drivers">Using Kernel-Mode Driver Framework with Miniport Drivers</a>.

The following code example deletes a specified miniport driver's framework driver object.


## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a>
</dt>
<dt>
<a href="..\wdfminiport\nf-wdfminiport-wdfdeviceminiportcreate.md">WdfDeviceMiniportCreate</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDriverMiniportUnload method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

