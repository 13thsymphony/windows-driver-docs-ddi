---
UID : NF:portcls.IMiniportTopology.Init
title : IMiniportTopology::Init method
author : windows-driver-content
description : The Init method initializes the topology miniport object.
old-location : audio\iminiporttopology_init.htm
old-project : audio
ms.assetid : c8c53792-8c1a-466a-9f0f-8c12f9e7b50e
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.iminiporttopology_init, portcls/IMiniportTopology::Init, audmp-routines_c87a11c3-aed3-4516-b3bf-5d32423fa293.xml, IMiniportTopology::Init, Init method [Audio Devices], IMiniportTopology interface, IMiniportTopology interface [Audio Devices], Init method, IMiniportTopology, Init method [Audio Devices], Init
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : Portcls.h
req.target-type : Universal
req.target-min-winverclnt : 
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
req.lib : portcls.h
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# Init method
The <code>Init</code> method initializes the topology miniport object.

## Syntax

````
NTSTATUS Init(
  [in] PUNKNOWN      UnknownAdapter,
  [in] PRESOURCELIST ResourceList,
  [in] PPORTTOPOLOGY Port
);
````

## Parameters

`UnknownAdapter`

Pointer to the <b>IUnknown</b> interface of the adapter object whose miniport object is being initialized. This parameter is optional and can be specified as <b>NULL</b>. For more information, see the following Remarks section.

`ResourceList`

Pointer to the <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a> interface of the resource list object that is to be supplied to the miniport driver during initialization. After passing this reference to the miniport driver, the port driver is free to examine the contents of the resource list but will not modify the contents of this list. For more information, see the following Remarks section.

`Port`

Pointer to the <a href="..\portcls\nn-portcls-iporttopology.md">IPortTopology</a> object that is bound to this miniport object. The caller specifies a valid, non-<b>NULL</b> pointer value for this parameter.


## Return Value

<code>Init</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

The <i>UnknownAdapter</i> and <i>ResourceList</i> parameters are the same pointer values that the adapter driver earlier passed as parameters to the <b>IPortTopology</b> object's <b>Init</b> method (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>).

The <i>UnknownAdapter</i>, <i>ResourceList</i>, and <i>Port</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h (include Portcls.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>

<a href="..\portcls\nn-portcls-iminiporttopology.md">IMiniportTopology</a>

<a href="..\portcls\nn-portcls-iporttopology.md">IPortTopology</a>

<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportTopology::Init method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>