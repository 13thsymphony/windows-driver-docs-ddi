---
UID : NS:wwan._WWAN_SMS_FILTER
title : "_WWAN_SMS_FILTER"
author : windows-driver-content
description : The WWAN_SMS_FILTER structure represents the filter to apply to SMS messages on the MB device.
old-location : netvista\wwan_sms_filter.htm
old-project : netvista
ms.assetid : 798101da-51be-416d-ac56-2f55a21e8ea8
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PWWAN_SMS_FILTER structure pointer [Network Drivers Starting with Windows Vista], PWWAN_SMS_FILTER, WwanRef_1bec8893-7ce8-4d8c-aea1-d1c76b0013fc.xml, WWAN_SMS_FILTER structure [Network Drivers Starting with Windows Vista], netvista.wwan_sms_filter, wwan/WWAN_SMS_FILTER, WWAN_SMS_FILTER, wwan/PWWAN_SMS_FILTER, *PWWAN_SMS_FILTER, _WWAN_SMS_FILTER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wwan.h
req.include-header : Wwan.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
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
req.typenames : WWAN_SMS_FILTER, *PWWAN_SMS_FILTER
req.product : Windows 10 or later.
---

# _WWAN_SMS_FILTER structure
The WWAN_SMS_FILTER structure represents the filter to apply to SMS messages on the MB device.

## Syntax
````
typedef struct _WWAN_SMS_FILTER {
  WWAN_SMS_FLAG Flag;
  ULONG         MessageIndex;
} WWAN_SMS_FILTER, *PWWAN_SMS_FILTER;
````

## Members


`Flag`

A value from the WWAN_SMS_FLAG enumeration that represents what filter to use to display SMS
     messages for.

`MessageIndex`

A value between 1 and 
     <i>ulMaxMessageIndex</i> that is an index into the device's message store.
     

This value in this member is valid only if 
     <b>Flag</b> is set to 
     <b>WwanSmsFlagIndex</b>. The MB Service sets this member if 
     <b>Flag</b> is set to 
     <b>WwanSmsFlagIndex</b>. For all flags other than 
     <b>WwanSmsFlagIndex</b>, the MB Service sets this index to WWAN_MESSAGE_INDEX_NONE.

## Remarks
When 
    <b>Flag</b> is 
    <b>WwanSmsFlagIndex</b>, the filter identifies the SMS message specified by 
    <b>MessageIndex</b> .

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_sms_read.md">WWAN_SMS_READ</a>

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_sms_delete.md">NDIS_WWAN_SMS_DELETE</a>

<a href="..\wwan\ne-wwan-_wwan_sms_flag.md">WWAN_SMS_FLAG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_FILTER structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>