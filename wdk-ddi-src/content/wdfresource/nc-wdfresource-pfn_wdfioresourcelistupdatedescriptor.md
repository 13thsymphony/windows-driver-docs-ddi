---
UID: NC:wdfresource.PFN_WDFIORESOURCELISTUPDATEDESCRIPTOR
title: PFN_WDFIORESOURCELISTUPDATEDESCRIPTOR function
author: windows-driver-content
description: The WdfIoResourceListUpdateDescriptor method updates a resource descriptor in a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistupdatedescriptor.htm
old-project: wdf
ms.assetid: a571c054-380d-4d56-9094-d55868222b33
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFIORESOURCELISTUPDATEDESCRIPTOR
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
req.alt-api: WdfIoResourceListUpdateDescriptor
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

# PFN_WDFIORESOURCELISTUPDATEDESCRIPTOR function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListUpdateDescriptor</b> method updates a resource descriptor in a resource requirements list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.



## -syntax

````
VOID WdfIoResourceListUpdateDescriptor(
  _In_ WDFIORESLIST            ResourceList,
  _In_ PIO_RESOURCE_DESCRIPTOR Descriptor,
  _In_ ULONG                   Index
);
````


## -parameters

### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


### -param Index [in]

A zero-based value that is used as an index into the set of resource descriptors that are already in the logical configuration that <i>ResourceList</i> specifies.


## -returns
None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks
The <b>WdfIoResourceListUpdateDescriptor</b> method locates the resource descriptor that the <i>Index</i> parameter identifies. Then the method copies the resource descriptor that the <i>Descriptor</i> parameter specifies into the descriptor that <i>Index</i> specifies.

For more information about resource requirements lists and logical configurations, see <a href="wdf.hardware_resources_for_kmdf_drivers">Hardware Resources for Framework-Based Drivers</a>.

The following code example initializes a new resource descriptor and then calls <b>WdfIoResourceListUpdateDescriptor</b> to replace the second descriptor in a logical configuration with the new descriptor.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceListUpdateDescriptor method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

