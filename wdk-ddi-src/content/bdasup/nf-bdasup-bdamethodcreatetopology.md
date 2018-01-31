---
UID : NF:bdasup.BdaMethodCreateTopology
title : BdaMethodCreateTopology function
author : windows-driver-content
description : The BdaMethodCreateTopology function creates a template topology between two pins of a filter.
old-location : stream\bdamethodcreatetopology.htm
old-project : stream
ms.assetid : 1f0e8fdc-ae3d-4f5e-b047-b3b7bf73d389
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : bdasup/BdaMethodCreateTopology, stream.bdamethodcreatetopology, BdaMethodCreateTopology function [Streaming Media Devices], BdaMethodCreateTopology, bdaref_3e082bad-4178-430a-aca0-3af6324a0aa2.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : bdasup.h
req.include-header : Bdasup.h
req.target-type : Desktop
req.target-min-winverclnt : Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---


# BdaMethodCreateTopology function
The <b>BdaMethodCreateTopology</b> function creates a template topology between two pins of a filter.

## Syntax

````
NTSTATUS BdaMethodCreateTopology(
  _In_ PIRP      Irp,
  _In_ PKSMETHOD pKSMethod,
       PVOID     pvIgnored
);
````

## Parameters

`pIrp`

TBD

`pKSMethod`

Points to a <a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a> structure that describes the method and request type of a method request.

`pvIgnored`

Points to a buffer that is ignored.


## Return Value

Returns STATUS_SUCCESS or an appropriate error code.

## Remarks

A BDA minidriver calls the <b>BdaMethodCreateTopology</b> function to create the template topology between two filter pins after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaMethodCreateTopology</b> function directly. Some BDA minidrivers must intercept this request, using an internal method (<a href="..\ks\nc-ks-pfnkshandler.md">KStrMethodHandler</a>), rather than dispatch it directly. These mindrivers must obtain a pointer to the BDA filter from the passed IRP before calling <b>BdaMethodCreateTopology</b> so that they can use the filter to keep track of associated pins. These mindrivers can then send instructions to the hardware when connecting particular pin types. See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/4af9efc3-8073-4111-9ad0-8b2fba4d1545">Configuring a BDA Filter</a> for more information. 

If a BDA minidriver must create the template topology between two filter pins without relying on the network provider, the BDA minidriver should call the <a href="..\bdasup\nf-bdasup-bdacreatetopology.md">BdaCreateTopology</a> function.

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

<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563413">KSMETHOD_BDA_CREATE_TOPOLOGY</a>

<a href="..\bdasup\nf-bdasup-bdacreatetopology.md">BdaCreateTopology</a>

<a href="..\ks\nc-ks-pfnkshandler.md">KStrMethodHandler</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaMethodCreateTopology function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>