---
UID: NF:bdasup.BdaDeletePin
title: BdaDeletePin function
author: windows-driver-content
description: The BdaDeletePin function deletes a pin from the specified filter.
old-location: stream\bdadeletepin.htm
old-project: stream
ms.assetid: 32ff70d7-980c-4c80-8ebc-af2121bc64df
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: BdaDeletePin
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BdaDeletePin
req.alt-loc: Bdasup.lib,Bdasup.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PKSP_BDA_NODE_PIN, KSP_BDA_NODE_PIN
---

# BdaDeletePin function



## -description
The <b>BdaDeletePin</b> function deletes a pin from the specified filter. 



## -syntax

````
NTSTATUS BdaDeletePin(
  _In_      PKSFILTER pKSFilter,
  _Out_opt_ PULONG    pulPinId
);
````


## -parameters

### -param pKSFilter [in]

Points to the filter in which to delete a pin.


### -param pulPinId [out, optional]

Points to a variable that contains the identifier for the pin to delete. 


## -returns
Returns STATUS_SUCCESS or an appropriate error code. 


## -remarks
A BDA minidriver calls the <a href="..\bdasup\nf-bdasup-bdamethoddeletepin.md">BdaMethodDeletePin</a> function when the network provider dynamically deletes a pin using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set. If a BDA minidriver must delete a pin without relying on the network provider, the BDA minidriver should call the <b>BdaDeletePin</b> function directly.


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
Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bdasup.h (include Bdasup.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Bdasup.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\bdasup\nf-bdasup-bdacreatepin.md">BdaCreatePin</a>
</dt>
<dt>
<a href="..\bdasup\nf-bdasup-bdamethoddeletepin.md">BdaMethodDeletePin</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaDeletePin function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

