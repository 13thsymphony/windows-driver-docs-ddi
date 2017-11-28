---
UID: NE.ntifs._OBJECT_INFORMATION_CLASS
title: OBJECT_INFORMATION_CLASS
author: windows-driver-content
description: The OBJECT_INFORMATION_CLASS enumeration type represents the type of information to supply about an object.
old-location: ifsk\object_information_class.htm
old-project: ifsk
ms.assetid: fbcca01d-2dd6-405a-9ec2-709652e9dcd6
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VOLUME_READ_PLEX_INPUT, VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Microsoft Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OBJECT_INFORMATION_CLASS
req.alt-loc: ntifs.h
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

# OBJECT_INFORMATION_CLASS enumeration



## -description
<p>The OBJECT_INFORMATION_CLASS enumeration type represents the type of information to supply about an object.</p>


## -syntax

````
typedef enum _OBJECT_INFORMATION_CLASS { 
  ObjectBasicInformation  = 0,
  ObjectTypeInformation   = 2
} OBJECT_INFORMATION_CLASS;
````


## -enum-fields
<dl>

### -field <a id="ObjectBasicInformation"></a><a id="objectbasicinformation"></a><a id="OBJECTBASICINFORMATION"></a><b>ObjectBasicInformation</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551944">PUBLIC_OBJECT_BASIC_INFORMATION</a> structure is supplied.</p>
</dd>

### -field <a id="ObjectTypeInformation"></a><a id="objecttypeinformation"></a><a id="OBJECTTYPEINFORMATION"></a><b>ObjectTypeInformation</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551947">PUBLIC_OBJECT_TYPE_INFORMATION</a> structure is supplied.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Microsoft Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551944">PUBLIC_OBJECT_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551947">PUBLIC_OBJECT_TYPE_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567062">ZwQueryObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20OBJECT_INFORMATION_CLASS enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
