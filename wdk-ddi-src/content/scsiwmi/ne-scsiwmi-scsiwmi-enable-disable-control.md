---
UID: NE.scsiwmi.SCSIWMI_ENABLE_DISABLE_CONTROL
title: SCSIWMI_ENABLE_DISABLE_CONTROL
author: windows-driver-content
description: The SCSIWMI_ENABLE_DISABLE_CONTROL enumerator is used to specify what to enable or disable.
old-location: storage\scsiwmi_enable_disable_control.htm
old-project: storage
ms.assetid: 0327bdc0-e4a4-4c2f-a9b9-5854e3330068
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SCSISCAN_INFO, SCSISCAN_INFO, *PSCSISCAN_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSIWMI_ENABLE_DISABLE_CONTROL
req.alt-loc: scsiwmi.h
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
req.iface: 
req.product: Windows 10 or later.
---

# SCSIWMI_ENABLE_DISABLE_CONTROL enumeration



## -description
<p>The SCSIWMI_ENABLE_DISABLE_CONTROL enumerator is used to specify what to enable or disable. </p>


## -syntax

````
typedef enum  { 
  ScsiWmiEventControl      = 0,
  ScsiWmiDataBlockControl  = 1
} SCSIWMI_ENABLE_DISABLE_CONTROL;
````


## -enum-fields
<dl>

### -field <a id="ScsiWmiEventControl"></a><a id="scsiwmieventcontrol"></a><a id="SCSIWMIEVENTCONTROL"></a><b>ScsiWmiEventControl</b>

<dd>
<p>Indicates that a WMI event is to be enabled or disabled. </p>
</dd>

### -field <a id="ScsiWmiDataBlockControl"></a><a id="scsiwmidatablockcontrol"></a><a id="SCSIWMIDATABLOCKCONTROL"></a><b>ScsiWmiDataBlockControl</b>

<dd>
<p>Indicates that a data collection for a block is to be enabled or disabled.  </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Scsiwmi.h (include Scsiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557338">HwScsiWmiFunctionControl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544094">DpWmiFunctionControl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSIWMI_ENABLE_DISABLE_CONTROL enumeration%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
