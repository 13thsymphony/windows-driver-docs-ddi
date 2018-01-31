---
UID : NF:bdasup.BdaPropertyNodeProperties
title : BdaPropertyNodeProperties function
author : windows-driver-content
description : The BdaPropertyNodeProperties function retrieves a list of properties that a node supports.
old-location : stream\bdapropertynodeproperties.htm
old-project : stream
ms.assetid : 1f50bf08-6134-4a97-8c9c-adc9ad697154
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : bdaref_fc328c79-7b0b-4646-91cd-3e4957b30b2a.xml, stream.bdapropertynodeproperties, bdasup/BdaPropertyNodeProperties, BdaPropertyNodeProperties function [Streaming Media Devices], BdaPropertyNodeProperties
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


# BdaPropertyNodeProperties function
The <b>BdaPropertyNodeProperties</b> function retrieves a list of properties that a node supports.

## Syntax

````
NTSTATUS BdaPropertyNodeProperties(
  _In_      PIRP      Irp,
  _In_      PKSP_NODE pKSProperty,
  _Out_opt_ GUID      *pguidProperty
);
````

## Parameters

`pIrp`

TBD

`pKSProperty`

Points to a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property and request type of the property request.

`pguidProperty`

Points to an array that receives the list of GUIDs for the properties supported by a node.


## Return Value

Returns STATUS_SUCCESS or an appropriate error code.

## Remarks

A BDA minidriver calls the <b>BdaPropertyNodeProperties</b> function to retrieve the list of properties for a node after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564330">KSPROPERTY_BDA_NODE_PROPERTIES</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyNodeProperties</b> function directly, without intercepting this request using an internal get-handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567177">KStrGetPropertyHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/fdac317e-d4fc-47c9-87d3-bec597f758f5">Determining BDA Device Topology</a> for more information.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564330">KSPROPERTY_BDA_NODE_PROPERTIES</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaPropertyNodeProperties function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>