---
UID: NS.USBFNBASE._USBFN_INTERFACE_INFO
title: _USBFN_INTERFACE_INFO
author: windows-driver-content
description: Describes an interface and its endpoints.
old-location: buses\usbfn_interface_info.htm
old-project: usbref
ms.assetid: 54647A9E-E0AB-4DE7-93FB-D0232D6AC646
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USBFN_INTERFACE_INFO, *PUSBFN_INTERFACE_INFO, USBFN_INTERFACE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnbase.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBFN_INTERFACE_INFO
req.alt-loc: usbfnbase.h
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
req.product: Windows 10 or later.
---

# _USBFN_INTERFACE_INFO structure



## -description
Describes an interface and its endpoints.



## -syntax

````
typedef struct _USBFN_INTERFACE_INFO {
  UINT8           InterfaceNumber;
  USBFN_BUS_SPEED Speed;
  USHORT           Size;
  UCHAR            InterfaceDescriptorSet[1];
} USBFN_INTERFACE_INFO, *PUSBFN_INTERFACE_INFO;
````


## -struct-fields

### -field InterfaceNumber

The index number of the interface.


### -field Speed

The operating bus speed indicated by <a href="buses.usbfn_bus_speed">USBFN_BUS_SPEED</a>-typed flags.


### -field  Size

Specifies the total length, in bytes, of all data for the interface. 


### -field  InterfaceDescriptorSet

Pointer to the first element in the array of that contains the interface descriptor set.  


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbfnbase.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.usbfn_bus_speed">USBFN_BUS_SPEED</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBFN_INTERFACE_INFO structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

