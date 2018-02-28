---
UID: NS:dot11wdi._NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
title: "_NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure defines the set of handlers that a WDI miniport driver must implement.
old-location: netvista\ndis_miniport_driver_wdi_characteristics.htm
old-project: netvista
ms.assetid: 2F69C228-FF2D-4277-A4C9-14FBADA1CD31
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, dot11wdi/NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, dot11wdi/PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, netvista.ndis_miniport_driver_wdi_characteristics"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	HeaderDef
api_location:
-	dot11wdi.h
api_name:
-	NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, *PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
---

# _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure
The NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure defines the set of handlers that a WDI miniport driver must implement. It is used by the IHV driver to register additional handlers for the control path and the full set of handlers for the data path.

## Syntax
````
typedef struct _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                            Header;
  ULONG                                         WdiVersion;
  MINIPORT_WDI_ALLOCATE_ADAPTER_HANDLER         AllocateAdapterHandler;
  MINIPORT_WDI_FREE_ADAPTER_HANDLER             FreeAdapterHandler;
  MINIPORT_WDI_OPEN_ADAPTER_HANDLER             OpenAdapterHandler;
  MINIPORT_WDI_CLOSE_ADAPTER_HANDLER            CloseAdapterHandler;
  MINIPORT_WDI_START_OPERATION_HANDLER          StartOperationHandler;
  MINIPORT_WDI_STOP_OPERATION_HANDLER           StopOperationHandler;
  MINIPORT_WDI_POST_PAUSE_HANDLER               PostPauseHandler;
  MINIPORT_WDI_POST_RESTART_HANDLER             PostRestartHandler;
  MINIPORT_WDI_HANG_DIAGNOSE_HANDLER            HangDiagnoseHandler;
  MINIPORT_WDI_TAL_TXRX_INITIALIZE_HANDLER      TalTxRxInitializeHandler;
  MINIPORT_WDI_TAL_TXRX_DEINITIALIZE_HANDLER    TalTxRxDeinitializeHandler;
  MINIPORT_WDI_IDLE_NOTIFICATION_HANDLER        LeIdleNotificationHandler;
  MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION_HANDLER LeCancelIdleNotificationHandler;
} NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, *PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS;
````

## Members


`AllocateAdapterHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_allocate_adapter.md">MiniportWdiAllocateAdapter</a> handler function.

`CloseAdapterHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_close_adapter.md">MiniportWdiCloseAdapter</a> handler function.

`FreeAdapterHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_free_adapter.md">MiniportWdiFreeAdapter</a> handler function.

`HangDiagnoseHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_adapter_hang_diagnose.md">MiniportWdiAdapterHangDiagnose</a> handler function.

`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_WDI_CHARACTERISTICS.
     

To indicate the version of the NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure, set the 
     <b>Revision</b> member to the following value:





#### NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS_REVISION_1

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_WDI_CHARACTERISTICS_REVISION_1.

`LeCancelIdleNotificationHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_cancel_idle_notification.md">MiniportWdiCancelIdleNotification</a> handler function.

`LeIdleNotificationHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_idle_notification.md">MiniportWdiIdleNotification</a> handler function.

`OpenAdapterHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_open_adapter.md">MiniportWdiOpenAdapter</a> handler function.

`PostPauseHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_post_adapter_pause.md">MiniportWdiPostAdapterPause</a> handler function.

`PostRestartHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_post_adapter_restart.md">MiniportWdiPostAdapterRestart</a> handler function.

`StartOperationHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_start_adapter_operation.md">MiniportWdiStartOperation</a> handler function.

`StopOperationHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_stop_adapter_operation.md">MiniportWdiStopOperation</a> handler function.

`TalTxRxDeinitializeHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_deinitialize.md">MiniportWdiTalTxRxDeinitialize</a> handler function.

`TalTxRxInitializeHandler`

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a> handler function.

`WdiVersion`

The version of WDI used by the driver. Set this member to one of the following values:





#### WDI_VERSION_LATEST

The latest WDI version



#### WDI_VERSION_1_0_1

WDI version 1.0.1



#### WDI_VERSION_1_0

WDI version 1.0


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h (include Ndis.h) |