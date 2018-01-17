---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER
title: EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER function
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER is called by the OS to get an OPM random number.
old-location: display\evt_idd_cx_monitor_opm_get_random_number.htm
old-project: display
ms.assetid: 330dc0a1-d9a9-44c1-9d29-752c2567e745
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFN_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
req.typenames: HWN_CLIENT_REGISTRATION_PACKET, *PHWN_CLIENT_REGISTRATION_PACKET
---

# EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER function



## -description
<b>EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER</b> is called by the OS to get an OPM random number.



## -syntax

````
EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER EvtIddCxMonitorOpmGetRandomNumber;

NTSTATUS EvtIddCxMonitorOpmGetRandomNumber(
  _In_  IDDCX_OPMCTX                     OpmCxtObject,
  _Out_ IDARG_OUT_OPM_GET_RANDOM_NUMBER* pOutArgs
)
{ ... }

typedef EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER PFN_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER;
````


## -parameters

### -param OpmCxtObject [in]


                    
                The object for the OPM context that a random number will be gotten from.


### -param pOutArgs [out]


                    
                Output arguments returned by <b>EVT_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER</b>.


## -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    


## -remarks
