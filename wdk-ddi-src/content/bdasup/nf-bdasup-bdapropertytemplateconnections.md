---
UID: NF.bdasup.BdaPropertyTemplateConnections
title: BdaPropertyTemplateConnections function
author: windows-driver-content
description: The BdaPropertyTemplateConnections function retrieves a list of connections that describe how pin types and node types are connected in a template topology.
old-location: stream\bdapropertytemplateconnections.htm
old-project: stream
ms.assetid: 64b55b53-677a-4977-b865-0a07d34d2530
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: BdaPropertyTemplateConnections
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
req.alt-api: BdaPropertyTemplateConnections
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
---

# BdaPropertyTemplateConnections function



## -description
The <b>BdaPropertyTemplateConnections</b> function retrieves a list of connections that describe how pin types and node types are connected in a template topology. 



## -syntax

````
NTSTATUS BdaPropertyTemplateConnections(
  _In_      PIRP                   Irp,
  _In_      PKSPROPERTY            pKSProperty,
  _Out_opt_ PKSTOPOLOGY_CONNECTION pConnectionProperty
);
````


## -parameters

### -param Irp [in]

Points to the IRP for the request to retrieve the list of connections. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564386">KSPROPERTY_BDA_TEMPLATE_CONNECTIONS</a> request.


### -param pKSProperty [in]

Points to a <a href="stream.ksproperty">KSPROPERTY</a> structure that describes the property and request type of the property request.


### -param pConnectionProperty [out, optional]

Points to an array that receives the list of <a href="stream.kstopology_connection">KSTOPOLOGY_CONNECTION</a> structures that describe the connections in a template topology. 


## -returns
Returns STATUS_SUCCESS or an appropriate error code. 


## -remarks
A BDA minidriver calls the <b>BdaPropertyTemplateConnections</b> function to retrieve the list of template connections after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564386">KSPROPERTY_BDA_TEMPLATE_CONNECTIONS</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyTemplateConnections</b> function directly, without intercepting this request using an internal get-handler (<a href="stream.kstrgetpropertyhandler">KStrGetPropertyHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/fdac317e-d4fc-47c9-87d3-bec597f758f5">Determining BDA Device Topology</a> for more information. 

The BDA minidriver provided a list of connections to the BDA support library in an array of <a href="stream.kstopology_connection">KSTOPOLOGY_CONNECTION</a> structures when the BDA minidriver passed the BDA filter template (<a href="stream.bda_filter_template">BDA_FILTER_TEMPLATE</a>) in <a href="stream.bdacreatefilterfactory">BdaCreateFilterFactory</a> and <a href="stream.bdainitfilter">BdaInitFilter</a> function calls. This array is a representation of all the possible connections between node and pin types that can be made within the filter or between the filter and adjoining filters. The <b>BdaPropertyTemplateConnections</b> function returns this array.


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
<a href="stream.bdacreatefilterfactory">BdaCreateFilterFactory</a>
</dt>
<dt>
<a href="stream.bda_filter_template">BDA_FILTER_TEMPLATE</a>
</dt>
<dt>
<a href="stream.bdainitfilter">BdaInitFilter</a>
</dt>
<dt>
<a href="stream.ksproperty">KSPROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564386">KSPROPERTY_BDA_TEMPLATE_CONNECTIONS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>
</dt>
<dt>
<a href="stream.kstopology_connection">KSTOPOLOGY_CONNECTION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaPropertyTemplateConnections function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

