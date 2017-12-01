---
UID: NS.bdasup._KSM_PIN_PAIR
title: KSM_PIN_PAIR
author: windows-driver-content
description: The KSM_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins.
old-location: stream\ksm_pin_pair.htm
old-project: stream
ms.assetid: a38e1215-4689-4b75-9a32-4d6570694b77
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KSM_PIN_PAIR, KSM_PIN_PAIR, *PKSM_PIN_PAIR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSM_PIN_PAIR
req.alt-loc: bdasup.h
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

# KSM_PIN_PAIR structure



## -description
<p>The KSM_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins. </p>


## -syntax

````
typedef struct _KSM_PIN_PAIR {
  KSMETHOD Method;
  ULONG    InputPinId;
  ULONG    OutputPinId;
  ULONG    Reserved;
} KSM_PIN_PAIR, *PKSM_PIN_PAIR;
````


## -struct-fields
<dl>

### -field <b>Method</b>

<dd>
<p>KSMETHOD structure that describes a method and request type of a method request.</p>
</dd>

### -field <b>InputPinId</b>

<dd>
<p>Identifier of an input pin of the filter.</p>
</dd>

### -field <b>OutputPinId</b>

<dd>
<p>Identifier of an output pin of the filter.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved.</p>
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
<dt>Bdasup.h (include Bdasup.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\bdasup\ns-bdasup--bda-pin-pairing.md">BDA_PIN_PAIRING</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSM_PIN_PAIR structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
