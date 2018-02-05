---
UID : NN:portcls.IAdapterPowerManagement3
title : IAdapterPowerManagement3
author : windows-driver-content
description : The IAdapterPowerManagement3 interface inherits from IUnknown, and it is used for receiving power management messages.
old-location : audio\iadapterpowermanagement3.htm
old-project : audio
ms.assetid : 5F0729DB-C991-4745-9550-9D25D6836A1F
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.iadapterpowermanagement3, IAdapterPowerManagement3 interface [Audio Devices], IAdapterPowerManagement3 interface [Audio Devices], described, IAdapterPowerManagement3, portcls/IAdapterPowerManagement3
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : portcls.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Portcls.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IAdapterPowerManagement3 interface

The IAdapterPowerManagement3 interface inherits from <b>IUnknown</b>, and it is used for receiving power management messages.

To register this interface with PortCls, the adapter driver must call  <a href="..\portcls\nf-portcls-pcregisteradapterpowermanagement.md">PcRegisterAdapterPowerManagement</a>.
<div class="alert"><b>Note</b>  If you want to fill the <a href="http://go.microsoft.com/fwlink/p/?linkid=143127">caps structure</a> for your device, your adapter driver can call <b>PcRegisterAdapterPowerManagement</b> from within the <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff540521(v=vs.85).aspx">AddDevice</a> routine, or before your driver calls <b>AddDevice.</b></div><div> </div>

## Methods

<p>The <b>IAdapterPowerManagement3</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [portcls.IAdapterPowerManagement3.D3ExitLatencyChanged](nf-portcls-iadapterpowermanagement3-d3exitlatencychanged.md) | PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Windows |
| **Header** | portcls.h |

## See Also

<a href="..\portcls\nn-portcls-iadapterpowermanagement2.md">IAdapterPowerManagement2</a>

<a href="..\portcls\nf-portcls-pcregisteradapterpowermanagement.md">PcRegisterAdapterPowerManagement</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IAdapterPowerManagement3 interface%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>