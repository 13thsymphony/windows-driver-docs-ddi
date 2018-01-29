---
UID : NF:sercx.SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION
title : SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION function
author : windows-driver-content
description : The SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION function initializes a SERCX2_SYSTEM_DMA_RECEIVE_CONFIG structure.
old-location : serports\sercx2_system_dma_receive_config_init_new_data_notification.htm
old-project : serports
ms.assetid : 01897D97-1507-4E48-A81E-2598B7C42357
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION, SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION function [Serial Ports], 2/SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION, serports.sercx2_system_dma_receive_config_init_new_data_notification
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : sercx.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows 8.1.
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : Any level.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SERCX_STATUS, *PSERCX_STATUS
req.product : Windows 10 or later.
---


# SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION function
The <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</b> function initializes a <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure.

## Syntax

````
VOID SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION(
  _Out_ SERCX2_SYSTEM_DMA_RECEIVE_CONFIG                           *Config,
  _In_  size_t                                                     MaximumTransferLength,
  _In_  PHYSICAL_ADDRESS                                           Address,
  _In_  DMA_WIDTH                                                  DmaWidth,
  _In_  PCM_PARTIAL_RESOURCE_DESCRIPTOR                            DmaDescriptor,
  _In_  PFN_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION EvtSerCx2SystemDmaReceiveEnableNewDataNotification,
  _In_  PFN_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION EvtSerCx2SystemDmaReceiveCancelNewDataNotification
);
````

## Parameters

`Config`

A pointer to the <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure that is to be initialized.

`MaximumTransferLength`

The value to load into the <b>MaximumTransferLength</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of the <b>MaximumTransferLength</b> member in <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

`Address`

The value to load into the <b>DeviceAddress</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

`DmaWidth`

The value to load into the <b>DmaWidth</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

`DmaDescriptor`

The value to load into the <b>DmaDescriptor</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

`EvtSerCx2SystemDmaReceiveEnableNewDataNotification`

The value to load into the <b>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</b> member of the <b>SERCX2_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

`EvtSerCx2SystemDmaReceiveCancelNewDataNotification`

The value to load into the <b>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</b> member of the <b>SERCX2_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.


## Return Value

None.

## Remarks

Your serial controller driver must use either this function or the <a href="..\sercx\nf-sercx-sercx2_system_dma_receive_config_init.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</a> function to initialize a <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> method.

<b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b>), and sets six additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</b> call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sercx.h |
| **Library** |  |
| **IRQL** | Any level. |
| **DDI compliance rules** |  |

## See Also

<a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a>

<a href="..\sercx\nf-sercx-sercx2_system_dma_receive_config_init.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</a>

<a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>