---
UID: NS.WINDOT11._DOT11_MAC_PARAMETERS
title: _DOT11_MAC_PARAMETERS
author: windows-driver-content
description: The DOT11_MAC_PARAMETERS is the optional input for an OID_DOT11_CREATE_MAC request. The device role is defined in an operation mode bitmask included in this structure.
old-location: netvista\dot11_mac_parameters.htm
old-project: netvista
ms.assetid: 53114ABE-33F2-4DA2-ABE0-2547547AA6AD
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DOT11_MAC_PARAMETERS, DOT11_MAC_PARAMETERS, *PDOT11_MAC_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_MAC_PARAMETERS
req.alt-loc: Windot11.h
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

# _DOT11_MAC_PARAMETERS structure



## -description

## -syntax

````
typedef struct _DOT11_MAC_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              uOpmodeMask;
} DOT11_MAC_PARAMETERS, *PDOT11_MAC_PARAMETERS;
````


## -struct-fields

### -field Header

The object header identifying the type and revision of this structure. The required member settings of <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> are the following:

### -field Type

<dd>
Must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>

### -field Revision

<dd>
Must be set to <b>DOT11_MAC_PARAMETERS_REVISION_1</b>

### -field Size

<dd>
Must be set to <b>DOT11_SIZEOF_MAC_PARAMETERS_REVISION_1</b>
</dd>
</dl>

### -field uOpmodeMask

A bitwise OR value of the operation modes Windows may set for the created port. This bitmask is defined through the following:


### -field DOT11_OPERATION_MODE_WFD_DEVICE

Specifies that the miniport driver supports the Wi-Fi Direct Device operation mode.

### -field DOT11_OPERATION_MODE_WFD_GROUP_OWNER

Specifies that the miniport driver supports the Wi-Fi Direct Group Owner operation mode.

### -field DOT11_OPERATION_MODE_WFD_CLIENT

Specifies that the miniport driver supports the Wi-Fi Direct Client operation mode.
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Versions: Supported in Windows 8
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Windot11.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569124">OID_DOT11_CREATE_MAC</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_MAC_PARAMETERS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
