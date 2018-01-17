---
UID: NC:wdfresource.PFN_WDFIORESOURCELISTGETCOUNT
title: PFN_WDFIORESOURCELISTGETCOUNT function
author: windows-driver-content
description: The WdfIoResourceListGetCount method returns the number of resource descriptors that are contained in a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistgetcount.htm
old-project: wdf
ms.assetid: d8f3d743-acc1-4884-b0ec-a6cea5d8e437
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFIORESOURCELISTGETCOUNT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfIoResourceListGetCount
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
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# PFN_WDFIORESOURCELISTGETCOUNT function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListGetCount</b> method returns the number of resource descriptors that are contained in a resource requirements list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.



## -syntax

````
ULONG WdfIoResourceListGetCount(
  _In_ WDFIORESLIST ResourceList
);
````


## -parameters

### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


## -returns
<b>WdfIoResourceListGetCount</b> returns the number of resource descriptors that are contained in the logical configuration that <i>ResourceList</i> specifies.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks
For more information about resource requirements lists and logical configurations, see <a href="wdf.hardware_resources_for_kmdf_drivers">Hardware Resources for Framework-Based Drivers</a>.

For a code example that uses <b>WdfIoResourceListGetCount</b>, see <a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistgetioreslist.md">WdfIoResourceRequirementsListGetIoResList</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistgetioreslist.md">WdfIoResourceRequirementsListGetIoResList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceListGetCount method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

