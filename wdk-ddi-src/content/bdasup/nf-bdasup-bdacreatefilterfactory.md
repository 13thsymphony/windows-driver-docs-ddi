---
UID : NF:bdasup.BdaCreateFilterFactory
title : BdaCreateFilterFactory function
author : windows-driver-content
description : The BdaCreateFilterFactory function adds the specified filter descriptor as a filter factory to the specified device and associates the filter factory with the specified BDA template topology.
old-location : stream\bdacreatefilterfactory.htm
old-project : stream
ms.assetid : bce1a41a-03fa-4f41-aeba-e18c85b07e00
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : BdaCreateFilterFactory
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : bdasup.h
req.include-header : Bdasup.h
req.target-type : Desktop
req.target-min-winverclnt : Available on Microsoft Windows XP and later operating systems. BdaCreateFilterFactory is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BdaCreateFilterFactory
req.alt-loc : Bdasup.lib,Bdasup.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Bdasup.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---


# BdaCreateFilterFactory function
The <b>BdaCreateFilterFactory</b> function adds the specified filter descriptor as a filter factory to the specified device and associates the filter factory with the specified BDA template topology.

## Syntax

````
NTSTATUS BdaCreateFilterFactory(
  _In_       PKSDEVICE           pKSDevice,
  _In_ const KSFILTER_DESCRIPTOR *pFilterDescriptor,
  _In_ const BDA_FILTER_TEMPLATE *pBdaFilterTemplate
);
````

## Parameters

`pKSDevice`

Points to the BDA device to which to add the filter factory with associated BDA template topology.

`pFilterDescriptor`

Points to a <a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a> structure that describes a filter for the BDA device. Note that not all of the template pin and node types may be exposed as pin and node factories when the filter is first initialized.

`pBdaFilterTemplate`

Points to a <a href="..\bdasup\ns-bdasup-_bda_filter_template.md">BDA_FILTER_TEMPLATE</a> structure that describes a BDA template topology.


## Return Value

Returns STATUS_SUCCESS or an appropriate error code.

## Remarks

A BDA minidriver calls the <b>BdaCreateFilterFactory</b> function to add a filter factory with an associated BDA template topology to a device and to register all of the topology's static template structures with the BDA support library (<i>BdaSup.sys</i>). The BDA support library can then handle the following method and property calls: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff563403">KSMETHODSETID_BdaChangeSync</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>


If a BDA minidriver requires a pointer to the newly created filter factory (<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>), the minidriver should call the <a href="..\bdasup\nf-bdasup-bdacreatefilterfactoryex.md">BdaCreateFilterFactoryEx</a> function instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdasup.h (include Bdasup.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\bdasup\nf-bdasup-bdacreatefilterfactoryex.md">BdaCreateFilterFactoryEx</a>
</dt>
<dt>
<a href="..\bdasup\ns-bdasup-_bda_filter_template.md">BDA_FILTER_TEMPLATE</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563403">KSMETHODSETID_BdaChangeSync</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaCreateFilterFactory function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>