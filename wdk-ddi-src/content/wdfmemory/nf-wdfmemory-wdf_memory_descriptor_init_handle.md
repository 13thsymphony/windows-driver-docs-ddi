---
UID: NF:wdfmemory.WDF_MEMORY_DESCRIPTOR_INIT_HANDLE
title: WDF_MEMORY_DESCRIPTOR_INIT_HANDLE function
author: windows-driver-content
description: The WDF_MEMORY_DESCRIPTOR_INIT_HANDLE function initializes a WDF_MEMORY_DESCRIPTOR structure so that it describes a specified framework memory object.
old-location: wdf\wdf_memory_descriptor_init_handle.htm
old-project: wdf
ms.assetid: e5449684-dd37-4d49-ae9f-372f295cecf8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_MEMORY_DESCRIPTOR_INIT_HANDLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_MEMORY_DESCRIPTOR_INIT_HANDLE
req.alt-loc: wdfmemory.h
req.ddi-compliance: MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctlA, MemAfterReqCompletedReadA, MemAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
req.product: Windows 10 or later.
---

# WDF_MEMORY_DESCRIPTOR_INIT_HANDLE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</b> function initializes a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure so that it describes a specified framework memory object.



## -syntax

````
VOID WDF_MEMORY_DESCRIPTOR_INIT_HANDLE(
  _Out_    PWDF_MEMORY_DESCRIPTOR Descriptor,
  _In_     WDFMEMORY              Memory,
  _In_opt_ PWDFMEMORY_OFFSET      Offsets
);
````


## -parameters

### -param Descriptor [out]

A pointer to a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure.


### -param Memory [in]

A handle to a framework memory object.


### -param Offsets [in, optional]

A pointer to a <a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure. This parameter is optional and can be <b>NULL</b>.


## -returns
None


## -remarks
The <b>WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</b> function zeros the specified <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure and sets the structure's <b>Type</b> member to <b>WdfMemoryDescriptorTypeHandle</b>. Then it sets the structure's <b>u.HandleType.Memory</b> and <b>u.HandleType.Offsets</b> members to the values that the <i>Memory</i> and <i>Offsets</i> parameters specify, respectively.

The following code example obtains a handle to a framework memory object that represents an I/O request's input buffer. The example uses the memory object handle to initialize a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure. Then, the example initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure and sends a USB control transfer request to an I/O target.


## -see-also
<dl>
<dt>
<a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_buffer.md">WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_mdl.md">WDF_MEMORY_DESCRIPTOR_INIT_MDL</a>
</dt>
<dt>
<a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_MEMORY_DESCRIPTOR_INIT_HANDLE function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

