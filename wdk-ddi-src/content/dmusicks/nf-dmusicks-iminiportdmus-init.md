---
UID: NF:dmusicks.IMiniportDMus.Init
title: IMiniportDMus::Init method
author: windows-driver-content
description: The Init method initializes the DMus miniport object.
old-location: audio\iminiportdmus_init.htm
old-project: audio
ms.assetid: 08111f70-d0cc-4abc-8bcd-86683af3eb32
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IMiniportDMus, IMiniportDMus interface [Audio Devices], Init method, IMiniportDMus::Init, Init method [Audio Devices], Init method [Audio Devices], IMiniportDMus interface, Init,IMiniportDMus.Init, audio.iminiportdmus_init, audmp-routines_016b2aed-13f3-4d9a-86c0-fbdbcbf55341.xml, dmusicks/IMiniportDMus::Init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dmusicks.h
api_name:
-	IMiniportDMus.Init
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---


# Init method
The <code>Init</code> method initializes the DMus miniport object.

## Syntax

````
NTSTATUS Init(
  [in, optional] PUNKNOWN      UnknownAdapter,
  [in]           PRESOURCELIST ResourceList,
  [in]           PPORTDMUS     Port,
  [out]          PSERVICEGROUP *ServiceGroup
);
````

## Parameters

`UnknownAdapter`

Pointer to the <b>IUnknown</b> interface of the adapter object whose miniport object is being initialized. This parameter is optional and can be specified as <b>NULL</b>. For more information, see the following Remarks section.

`ResourceList`

Pointer to an <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a> object that contains the adapter's resource list. After passing this reference to the miniport driver, the port driver is free to examine the contents of the resource list but will not modify the contents of this list.

`Port`

Pointer to an <a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a> object that provides the port driver's callback interface.

`ServiceGroup`

Output pointer for the service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> interface of the miniport driver's service group object. This is the service group that this miniport driver wants to have used for calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536880">IPortDMus::Notify</a>.


## Return Value

<code>Init</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

The <i>pUnknownAdapter</i> parameter is optional:

<ul>
<li>
If <i>pUnknownAdapter</i> is non-<b>NULL</b>, the <code>Init</code> method queries the <i>pUnknownAdapter</i> object for its <a href="..\portcls\nn-portcls-iinterruptsync.md">IInterruptSync</a> interface.

</li>
<li>
If <i>pUnknownAdapter</i> is <b>NULL</b>, the <code>Init</code> method calls <a href="..\portcls\nf-portcls-pcnewinterruptsync.md">PcNewInterruptSync</a> to create a new <b>IInterruptSync</b> object. In this case, the resource list that <i>pResourceList</i> points to supplies the interrupt resource that the new <b>IInterruptSync</b> object uses.

</li>
</ul>
In either case, the <code>Init</code> method and calls the <b>RegisterServiceRoutine</b> method on the <b>IInterruptSync</b> object in order to add the miniport driver's interrupt service routine (ISR) to the list of ISRs. When the adapter driver later frees the port object, the port driver releases its reference to the <b>IInterruptSync</b> object.

The <i>pUnknownAdapter</i> and <i>pResourceList</i> parameters are the same pointer values that the adapter driver earlier passed as parameters to the <b>IPortDMus</b> object's <code>Init</code> method (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>).

The <i>pUnknownAdapter</i>, <i>pResourceList</i>, <i>pPort</i>, and <i>ppServiceGroup</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dmusicks.h (include Dmusicks.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\portcls\nn-portcls-iinterruptsync.md">IInterruptSync</a>



<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>



<a href="..\dmusicks\nn-dmusicks-iminiportdmus.md">IMiniportDMus</a>



<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536880">IPortDMus::Notify</a>



<a href="..\portcls\nf-portcls-pcnewinterruptsync.md">PcNewInterruptSync</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>



<a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a>