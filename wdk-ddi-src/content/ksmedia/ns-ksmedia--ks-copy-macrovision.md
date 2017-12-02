---
UID: NS.ksmedia._KS_COPY_MACROVISION
title: KS_COPY_MACROVISION
author: windows-driver-content
description: The KS_COPY_MACROVISION structure specifies the Macrovision level of the data stream.
old-location: stream\ks_copy_macrovision.htm
old-project: stream
ms.assetid: 86c6ee78-ae4e-4b96-be83-a5960f36a363
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KS_COPY_MACROVISION, KS_COPY_MACROVISION, *PKS_COPY_MACROVISION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_COPY_MACROVISION
req.alt-loc: ksmedia.h
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
---

# KS_COPY_MACROVISION structure



## -description
<p>The KS_COPY_MACROVISION structure specifies the Macrovision level of the data stream.</p>


## -syntax

````
typedef struct _KS_COPY_MACROVISION {
  ULONG MACROVISIONLevel;
} KS_COPY_MACROVISION, *PKS_COPY_MACROVISION;
````


## -struct-fields
<dl>

### -field MACROVISIONLevel

<dd>
<p>Specifies the Macrovision level. This must be one of the following values from the KS_COPY_MACROVISION_LEVEL enumeration:</p>
<table>
<tr>
<th>Level</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>KS_MACROVISION_DISABLED</p>
</td>
<td>
<p>Indicates that Macrovision copyright protection should not be in effect.</p>
</td>
</tr>
<tr>
<td>
<p>KS_MACROVISION_LEVEL1</p>
</td>
<td>
<p>Indicates that Macrovision level 1 copyright protection must be in effect.</p>
</td>
</tr>
<tr>
<td>
<p>KS_MACROVISION_LEVEL2</p>
</td>
<td>
<p>Indicates that Macrovision level 2 copyright protection must be in effect.</p>
</td>
</tr>
<tr>
<td>
<p>KS_MACROVISION_LEVEL3</p>
</td>
<td>
<p>Indicates that Macrovision level 3 copyright protection must be in effect.</p>
</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -remarks
<p>The KS_COPY_MACROVISION structure is used by the KSPROPERTY_COPY_MACROVISION property.</p>

<p>For additional uses of this structure see <a href="https://msdn.microsoft.com/ff9cf8c8-7c8f-485c-b2ab-7567a5eeb87b">DVD Copyright Protection</a> and <a href="https://msdn.microsoft.com/62bd8d8a-3e58-4bca-a32d-ff792180afbe">Macrovision</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565114">KSPROPERTY_COPY_MACROVISION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_COPY_MACROVISION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
