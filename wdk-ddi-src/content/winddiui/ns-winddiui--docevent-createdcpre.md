---
UID: NS.winddiui._DOCEVENT_CREATEDCPRE
title: DOCEVENT_CREATEDCPRE
author: windows-driver-content
description: The DOCEVENT_CREATEDCPRE structure contains a set of values used in certain calls to DrvDocumentEvent and IPrintOemUI2::DocumentEvent.
old-location: print\docevent_createdcpre.htm
ms.assetid: ad95d11e-c170-4c21-a498-45e38f41cbbb
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: print
req.header: winddiui.h
req.include-header: Winddiui.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOCEVENT_CREATEDCPRE
req.alt-loc: winddiui.h
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
ms.keywords: DOCEVENT_CREATEDCPRE, DOCEVENT_CREATEDCPRE, *PDCEVENT_CREATEDCPRE
req.iface: 
req.product: Windows 10 or later.
---

# DOCEVENT_CREATEDCPRE structure



## -description
<p>The DOCEVENT_CREATEDCPRE structure contains a set of values used in certain calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548544">DrvDocumentEvent</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554141">IPrintOemUI2::DocumentEvent</a>.</p>


## -syntax

````
typedef struct _DOCEVENT_CREATEDCPRE {
  PWSTR     pszDriver;
  PWSTR     pszDevice;
  PDEVMODEW pdm;
  BOOL      bIC;
} DOCEVENT_CREATEDCPRE, *PDCEVENT_CREATEDCPRE;
````


## -struct-fields
<dl>

### -field <b>pszDriver</b>

<dd>
<p>Reserved for system use. Set to zero.</p>
</dd>

### -field <b>pszDevice</b>

<dd>
<p>Pointer to the first byte of a Unicode string that contains either the device name or the port name, depending on whether print spooling is enabled or disabled. If the print job is being sent directly to the printer (spooling is disabled), this member contains the printer name. If a print job is being spooled, this member contains the port name. </p>
</dd>

### -field <b>pdm</b>

<dd>
<p>Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure passed to either CreateIC or CreateDC (both described in the Microsoft Windows SDK documentation). This member can be <b>NULL</b>.</p>
</dd>

### -field <b>bIC</b>

<dd>
<p>Specifies whether the DEVMODEW structure pointed to by the <b>pdm</b> member is being passed to CreateIC or CreateDC. If <b>TRUE</b>, CreateIC is being called. If <b>FALSE</b>, CreateDC is being called.</p>
</dd>
</dl>

## -remarks
<p>The DOCEVENT_CREATEDCPRE structure is defined for Windows XP and later.</p>

<p>This structure is used in conjunction with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548544">DrvDocumentEvent</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff554141">IPrintOemUI2::DocumentEvent</a>, in which the <i>iEsc</i> parameter is set to DOCUMENTEVENT_CREATEDCPRE. Before calling either of these functions, the caller must fill in the members of this structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Winddiui.h (include Winddiui.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548544">DrvDocumentEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554141">IPrintOemUI2::DocumentEvent</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DOCEVENT_CREATEDCPRE structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
