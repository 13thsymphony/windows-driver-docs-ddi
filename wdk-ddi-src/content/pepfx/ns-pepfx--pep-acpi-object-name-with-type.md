---
UID: NS.pepfx._PEP_ACPI_OBJECT_NAME_WITH_TYPE
title: PEP_ACPI_OBJECT_NAME_WITH_TYPE
author: windows-driver-content
description: The PEP_ACPI_OBJECT_NAME_WITH_TYPE structure that specifies both the path-relative name of an ACPI object and the type of this object.
old-location: kernel\pep_acpi_object_name_with_type.htm
old-project: kernel
ms.assetid: 7DD01461-4890-4095-A55C-771EA0EEA642
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PEP_ACPI_OBJECT_NAME_WITH_TYPE, PEP_ACPI_OBJECT_NAME_WITH_TYPE, *PPEP_ACPI_OBJECT_NAME_WITH_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_ACPI_OBJECT_NAME_WITH_TYPE
req.alt-loc: pepfx.h
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
req.iface: 
---

# PEP_ACPI_OBJECT_NAME_WITH_TYPE structure



## -description
<p>The <b>PEP_ACPI_OBJECT_NAME_WITH_TYPE</b> structure that specifies both the path-relative name of an ACPI object and the type of this object.</p>


## -syntax

````
typedef struct _PEP_ACPI_OBJECT_NAME_WITH_TYPE {
  PEP_ACPI_OBJECT_NAME Name;
  PEP_ACPI_OBJECT_TYPE Type;
} PEP_ACPI_OBJECT_NAME_WITH_TYPE, *PPEP_ACPI_OBJECT_NAME_WITH_TYPE;
````


## -struct-fields
<dl>

### -field Name

<dd>
<p>A <a href="..\pepfx\ns-pepfx--pep-acpi-object-name.md">PEP_ACPI_OBJECT_NAME</a> structure that contains the four-character name of the ACPI object.</p>
</dd>

### -field Type

<dd>
<p>A <a href="..\pepfx\ne-pepfx--pep-acpi-object-type.md">PEP_ACPI_OBJECT_TYPE</a> enumeration value that indicates the type of ACPI object. Currently, the only supported object type is a control method.</p>
</dd>
</dl>

## -remarks
<p>The <b>Objects</b> member of the <a href="..\pepfx\ns-pepfx--pep-acpi-enumerate-device-namespace.md">PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</a> structure is the first element in an array of <b>PEP_ACPI_OBJECT_NAME_WITH_TYPE</b> structures.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\pepfx\ns-pepfx--pep-acpi-enumerate-device-namespace.md">PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx--pep-acpi-object-name.md">PEP_ACPI_OBJECT_NAME</a>
</dt>
<dt>
<a href="..\pepfx\ne-pepfx--pep-acpi-object-type.md">PEP_ACPI_OBJECT_TYPE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_OBJECT_NAME_WITH_TYPE structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
