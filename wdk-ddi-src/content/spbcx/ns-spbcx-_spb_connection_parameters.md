---
UID : NS:spbcx._SPB_CONNECTION_PARAMETERS
title : _SPB_CONNECTION_PARAMETERS
author : windows-driver-content
description : The SPB_CONNECTION_PARAMETERS structure contains the connection parameters for a target device on a simple peripheral bus.
old-location : spb\spb_connection_parameters.htm
old-project : SPB
ms.assetid : 4707b797-6759-426d-89eb-01215af6ce19
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SPB.spb_connection_parameters, PSPB_CONNECTION_PARAMETERS, SPB_CONNECTION_PARAMETERS structure [Buses], _SPB_CONNECTION_PARAMETERS, *PSPB_CONNECTION_PARAMETERS, spbcx/PSPB_CONNECTION_PARAMETERS, spbcx/SPB_CONNECTION_PARAMETERS, PSPB_CONNECTION_PARAMETERS structure pointer [Buses], SPB_CONNECTION_PARAMETERS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : spbcx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 8.
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
req.lib : 
req.dll : 
req.irql : Any IRQL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SPB_CONNECTION_PARAMETERS, *PSPB_CONNECTION_PARAMETERS
req.product : Windows 10 or later.
---

# _SPB_CONNECTION_PARAMETERS structure
The <b>SPB_CONNECTION_PARAMETERS</b> structure contains the connection parameters for a target device on a <a href="https://msdn.microsoft.com/2c660e14-5b27-4610-a328-735b07ed0773">simple peripheral bus</a>.

## Syntax
````
typedef struct SPB_CONNECTION_PARAMETERS {
  USHORT Size;
  PCWSTR ConnectionTag;
  PVOID  ConnectionParameters;
} SPB_CONNECTION_PARAMETERS, *PSPB_CONNECTION_PARAMETERS;
````

## Members


`ConnectionParameters`

A pointer to the connection parameters for this target. This member points to a memory buffer that contains the target-specific parameters that the SPB controller driver needs to communicate with the target. For more information, see the following Remarks section.

`ConnectionTag`

A pointer to the connection tag for this target. The connection tag is an opaque string that contains a connection ID that identifies the connection of the target device to the bus. For more information, see <a href="https://msdn.microsoft.com/234B5858-5930-40AD-BE4C-4A774A809D10">Connection IDs for SPB-Connected Peripheral Devices</a>.

`Size`

The size, in bytes, of this structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/hh450926">SpbTargetGetConnectionParameters</a> method uses the <b>Size</b> value to determine which version of this structure is being used. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406205">SPB_CONNECTION_PARAMETERS_INIT</a> function to initialize this member. For more information, see the following Remarks section.

## Remarks
This structure contains information about the connection of a target device to the bus. When a client (peripheral driver) opens a logical connection to the target device, the SPB controller driver retrieves the connection settings for the device and stores these settings. Later, in response to an I/O request from the client to the device, the SPB controller driver uses the connection settings to configure the controller to access the device over the bus.

For example, the connection settings for a device on an I2C bus include the following:
<ul>
<li>The bus-relative address of the target device.</li>
<li>The number of address bits to use to access the target device.</li>
<li>The bus clock frequency to use to access the target device.</li>
</ul>The <b>ConnectionParameters</b> member of the <b>SPB_CONNECTION_PARAMETERS</b> structure is a pointer to a buffer that contains the connection settings for a target device on the bus. For a code example that uses the <b>ConnectionParameters</b> member to get these connection parameters, see <a href="https://msdn.microsoft.com/B614993A-0EA9-4B91-A336-80EEF9BE3E69">How to Get the Connection Settings for a Device</a>.

Call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450926">SpbTargetGetConnectionParameters</a> method to get the connection parameters for an SPBTARGET handle that represents the target device. This method writes the connection parameters to a caller-supplied <b>SPB_CONNECTION_PARAMETERS</b> structure. Before passing this structure to <b>SpbTargetGetConnectionParameters</b>, initialize the structure by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406205">SPB_CONNECTION_PARAMETERS_INIT</a> function.

To open a connection on behalf of a client (peripheral driver), the SPB framework extension (SpbCx) calls your SPB controller driver's <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> callback function. To close the connection, SpbCx calls the SPB controller driver's <a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a> callback function. An SPB controller driver typically calls <b>SpbTargetGetConnectionParameters</b> from the driver's <i>EvtSpbTargetConnect</i> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | spbcx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450926">SpbTargetGetConnectionParameters</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj938063">RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</a>

<a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a>

<a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406205">SPB_CONNECTION_PARAMETERS_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_CONNECTION_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>