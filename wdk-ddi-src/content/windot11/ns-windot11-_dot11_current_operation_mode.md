---
UID : NS:windot11._DOT11_CURRENT_OPERATION_MODE
title : _DOT11_CURRENT_OPERATION_MODE
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11_current_operation_mode.htm
old-project : netvista
ms.assetid : 085ee8f4-7e96-416a-a59f-f35c8ad0dbf4
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : DOT11_CURRENT_OPERATION_MODE, netvista.dot11_current_operation_mode, PDOT11_CURRENT_OPERATION_MODE structure pointer [Network Drivers Starting with Windows Vista], _DOT11_CURRENT_OPERATION_MODE, DOT11_CURRENT_OPERATION_MODE structure [Network Drivers Starting with Windows Vista], windot11/PDOT11_CURRENT_OPERATION_MODE, Native_802.11_data_types_d2f0f1a7-3e89-4ac1-acbd-a032909837a2.xml, PDOT11_CURRENT_OPERATION_MODE, windot11/DOT11_CURRENT_OPERATION_MODE, *PDOT11_CURRENT_OPERATION_MODE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : windot11.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DOT11_CURRENT_OPERATION_MODE, *PDOT11_CURRENT_OPERATION_MODE
req.product : Windows 10 or later.
---

# _DOT11_CURRENT_OPERATION_MODE structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_CURRENT_OPERATION_MODE structure defines the current Native 802.11 operation mode on the
  instance of a miniport driver that manages a wireless LAN (WLAN) adapter.

## Syntax
````
typedef struct _DOT11_CURRENT_OPERATION_MODE {
  ULONG uReserved;
  ULONG uCurrentOpMode;
} DOT11_CURRENT_OPERATION_MODE, *PDOT11_CURRENT_OPERATION_MODE;
````

## Members


`uCurrentOpMode`

A bitmask of the miniport driver's current operation modes. This bitmask is defined through the
      following:



For more information about operation modes, see 
      <mshelp:link keywords="netvista.native_802_11_operation_modes" tabindex="0">Native 802.11 Operation
      Modes</mshelp:link>.

`uReserved`

This member is reserved. The miniport driver must not modify the value of this member.

## Remarks
The miniport driver must specify only one operation mode in the 
    <b>uCurrentOpMode</b> member.

For more information about Native 802.11 operation modes, see 
    <mshelp:link keywords="netvista.native_802_11_operation_modes" tabindex="0">Native 802.11 Operation
    Modes</mshelp:link>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | windot11.h (include Ndis.h) |

## See Also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation Modes</a>

<mshelp:link keywords="netvista.oid_dot11_current_operation_mode" tabindex="0">
   OID_DOT11_CURRENT_OPERATION_MODE</mshelp:link>

<a href="..\wlclient\ns-wlclient-_dot11_adapter.md">DOT11_ADAPTER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_CURRENT_OPERATION_MODE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>