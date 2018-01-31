---
UID : NF:ksproxy.IKsTopology.CreateNodeInstance
title : IKsTopology::CreateNodeInstance method
author : windows-driver-content
description : The CreateNodeInstance method requests a KS filter object to open a topology node object.
old-location : stream\ikstopology_createnodeinstance.htm
old-project : stream
ms.assetid : 882b47c2-8fbe-4de0-8ef3-206faaf1e990
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : CreateNodeInstance method [Streaming Media Devices], CreateNodeInstance method [Streaming Media Devices], IKsTopology interface, IKsTopology interface [Streaming Media Devices], CreateNodeInstance method, CreateNodeInstance, IKsTopology::CreateNodeInstance, stream.ikstopology_createnodeinstance, ksproxy/IKsTopology::CreateNodeInstance, IKsTopology, ksproxy_91ff533c-4aa9-43db-9165-1c0c6f395393.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : ksproxy.h
req.include-header : Ksproxy.h
req.target-type : DesktopMobile
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
req.lib : ksproxy.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PIPE_STATE
---


# CreateNodeInstance method
The <b>CreateNodeInstance</b> method requests a KS filter object to open a topology node object.

## Syntax

````
HRESULT CreateNodeInstance(
  [in]           ULONG       NodeId,
  [in]           ULONG       Flags,
  [in]           ACCESS_MASK DesiredAccess,
  [in, optional] IUnknown    *UnkOuter,
  [in]           REFGUID     InterfaceId,
  [out]          LPVOID      *Interface
);
````

## Parameters

`NodeId`

Identifier for the topology node object to open.

`Flags`

A bitmask enumerating the type of topology node object. No flags are currently defined.

`DesiredAccess`

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> bitmask specifying the type of access that the caller requires to the topology node object. See <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> for a description of each access-right value.

`UnkOuter`

Pointer to an <b>IUnknown</b> interface that supports the topology node interface.

`InterfaceId`

Identifier of the topology node interface being requested.

`Interface`

Pointer to a variable that receives the interface pointer requested in <i>InterfaceId</i>. Upon successful return, *<i>Interface</i> contains the requested interface pointer to the object. If the object does not support the interface specified in <i>InterfaceId</i>, *<i>Interface</i> is set to <b>NULL</b>.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | DesktopMobile |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>

<a href="..\ksproxy\nn-ksproxy-ikstopology.md">IKsTopology</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsTopology::CreateNodeInstance method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>