---
UID: NC:dot11wdi.MINIPORT_WDI_POST_ADAPTER_RESTART
title: MINIPORT_WDI_POST_ADAPTER_RESTART
author: windows-driver-content
description: The MiniportWdiPostAdapterRestart handler function is called by the Microsoft component after it finishes restarting the data path as part of the NDIS MiniportRestart requirements.
old-location: netvista\miniportwdipostadapterrestart.htm
old-project: netvista
ms.assetid: 1686A3CA-AD4A-4560-8665-9AFBE920CDDA
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _SYNTH_STATS, *PSYNTH_STATS, SYNTH_STATS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportWdiPostAdapterRestart
req.alt-loc: dot11wdi.h
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
req.typenames: *PSYNTH_STATS, SYNTH_STATS
---

# MINIPORT_WDI_POST_ADAPTER_RESTART callback



## -description
The MiniportWdiPostAdapterRestart handler function is called by the Microsoft component after it finishes restarting the data path as part of the NDIS <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> requirements.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.

The NDIS <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> requirements are handled by the Microsoft component. As part of <i>MiniportRestart</i>, it undoes the data path pause work that it performed as part of <a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a>. The WDI IHV miniport can optionally register for a <i>MiniportWdiPostAdapterRestart</i> callback that is called by the Microsoft component after it finishes restarting the data path.



## -prototype

````
MINIPORT_WDI_POST_ADAPTER_RESTART MiniportWdiPostAdapterRestart;

NDIS_STATUS MiniportWdiPostAdapterRestart(
  _In_ NDIS_HANDLE                       MiniportAdapterContext,
  _In_ PNDIS_MINIPORT_RESTART_PARAMETERS RestartParameters
)
{ ... }
````


## -parameters

### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


### -param RestartParameters [in]

A pointer to an <a href="..\ndis\ns-ndis-_ndis_miniport_restart_parameters.md">NDIS_MINIPORT_RESTART_PARAMETERS</a> structure that defines the restart parameters for the miniport adapter.


## -returns
MiniportWdiPostAdapterRestart can return any of the following return values.
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The driver successfully restarted the flow of network data through the miniport adapter.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>The restart failed because of insufficient resources.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>The driver indicates <b>NDIS_STATUS_FAILURE</b> if none of the preceding values applies.

 

To define a MiniportWdiPostAdapterRestart function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiPostAdapterRestart function that is named "MyPostAdapterRestart", use the <b>MINIPORT_WDI_POST_ADAPTER_RESTART</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_WDI_POST_ADAPTER_RESTART</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_POST_ADAPTER_RESTART</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a>
</dt>
<dt>
<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_restart_parameters.md">NDIS_MINIPORT_RESTART_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_POST_ADAPTER_RESTART callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

