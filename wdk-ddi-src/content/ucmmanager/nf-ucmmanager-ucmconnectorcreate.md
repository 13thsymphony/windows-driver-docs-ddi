---
UID : NF:ucmmanager.UcmConnectorCreate
title : UcmConnectorCreate function
author : windows-driver-content
description : Creates a connector object.
old-location : buses\ucmconnectorcreate.htm
old-project : usbref
ms.assetid : 1376CB84-05F6-4903-B245-A00CFA9B228E
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : buses.ucmconnectorcreate, ucmmanager/UcmConnectorCreate, UcmConnectorCreate, UcmConnectorCreate method [Buses]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ucmmanager.h
req.include-header : Ucmcx.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 1.15
req.umdf-ver : 2.15
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : UcmCxstub.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPORT_DATA_1, PORT_DATA_1"
req.product : Windows 10 or later.
---


# UcmConnectorCreate function
Creates a connector object.

## Syntax

````
NTSTATUS UcmConnectorCreate(
  [in]  WDFDEVICE              WdfDevice,
  [in]  PUCM_CONNECTOR_CONFIG  Config,
  [in]  PWDF_OBJECT_ATTRIBUTES Attributes,
  [out] UCMCONNECTOR           *Connector
);
````

## Parameters

`WdfDevice`

A handle to a framework device object that the client driver received in the previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

`Config`

A pointer to a caller-supplied <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_config.md">UCM_CONNECTOR_CONFIG</a> structure that is initialized by calling <a href="..\ucmmanager\nf-ucmmanager-ucm_connector_config_init.md">UCM_CONNECTOR_CONFIG_INIT</a>.

`Attributes`

A pointer to a caller-supplied <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new connector object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

`Connector`

A pointer to a location that receives a handle to the new connector object.


## Return Value

<b>UcmConnectorCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value.

## Remarks

If the client driver specifies a connector identifier that is already in use, the method fails with STATUS_INVALID_PARAMETER error code.

If the Type-C connector is specified to be a Dual-Role port (DRP), the client driver must register its <a href="..\ucmmanager\nc-ucmmanager-evt_ucm_connector_set_data_role.md">EVT_UCM_CONNECTOR_SET_DATA_ROLE</a> event callback.  

The parent object is WdfDevice. You can set the <b>ParentObject</b> member of <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> to NULL or the WDFDEVICE handle. The connector object gets deleted when the parent WDFDEVICE object gets deleted.

An appropriate place for a UCM client driver to call <b>UcmConnectorCreate</b> is in <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>  or <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a>. Conversely, the driver should release the UCMCONNECTOR  handle in  <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> or <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmmanager.h (include Ucmcx.h) |
| **Library** | UcmCxstub.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ucmmanager\nf-ucmmanager-ucm_connector_config_init.md">UCM_CONNECTOR_CONFIG_INIT</a>

<a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_config.md">UCM_CONNECTOR_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmConnectorCreate method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>