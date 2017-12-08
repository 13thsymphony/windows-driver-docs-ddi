---
UID: NC.ntddk.PGET_LOCATION_STRING
title: PGET_LOCATION_STRING
author: windows-driver-content
description: The PnpGetLocationString routine provides the device-specific part of the device's SPDRP_LOCATION_PATHS property.
old-location: kernel\pnpgetlocationstring.htm
old-project: kernel
ms.assetid: 03ebdeed-10f0-4633-a9cd-4db683a8c3a7
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Server 2003.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PnpGetLocationString
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
---

# PGET_LOCATION_STRING callback



## -description
The <i>PnpGetLocationString</i> routine provides the device-specific part of the device's SPDRP_LOCATION_PATHS property.


## -prototype

````
PGET_LOCATION_STRING PnpGetLocationString;

NTSTATUS PnpGetLocationString(
  _Inout_ PVOID  Context,
  _Out_   PWCHAR *LocationStrings
)
{ ... }
````


## -parameters

### -param Context [in, out]

A pointer to interface-specific context information.  The caller passes the value that is passed as the <b>Context</b> member of the <a href="kernel.pnp_location_interface">PNP_LOCATION_INTERFACE</a> structure.

### -param LocationStrings [out]

A pointer to a sequence of null-terminated Unicode strings, that is terminated by another zero. Each string serves as a location string for the device. Drivers typically return a single string.

## -returns
The routine returns an NTSTATUS value to indicate the status of the operation.

## -remarks
The <a href="kernel.pnp_location_interface">PNP_LOCATION_INTERFACE</a> structure supplies a pointer to the <i>PnpGetLocationString</i> routine.

The <i>PnpGetLocationString</i> routine provides the device-specific part of the location string for the device.  The Plug and Play (PnP) manager assembles the location string for a device by querying the driver for the device, for the device's bus, and any parent buses, and concatenating the provided strings together.

The routine must return a string that is unique to the device relative to its bus. The string must be the same for the device across all versions of the operating system. Once you select a string for this purpose, you must not change it.

By convention, the location string takes the form <i>ServiceName(BusSpecificLocation)</i>. For example, PCI devices use PCI(<i>XXYY</i>), where <i>XX</i> is the device number, and <i>YY</i> is the function number.

The <i>PnpGetLocationString</i> routine calls a routine such as <a href="kernel.exallocatepoolwithtag">ExAllocatePoolWithTag</a> to allocate the memory for the location string. The caller is responsible for calling the <a href="kernel.exfreepool">ExFreePool</a> routine to free the memory pointed to by <i>LocationStrings</i> when the location string is no longer needed.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows Server 2003.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exallocatepoolwithtag">ExAllocatePoolWithTag</a>
</dt>
<dt>
<a href="kernel.exfreepool">ExFreePool</a>
</dt>
<dt>
<a href="kernel.pnp_location_interface">PNP_LOCATION_INTERFACE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PGET_LOCATION_STRING routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
