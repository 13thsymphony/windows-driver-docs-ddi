---
UID: NE.avc._tagAVC_FUNCTION
title: _tagAVC_FUNCTION
author: windows-driver-content
description: The AVC_FUNCTION enumeration type is used to specify AV/C subunit functions.
old-location: stream\avc_function.htm
old-project: stream
ms.assetid: 31451163-bc60-4c84-88a7-e11edea97436
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _tagAVC_FUNCTION, AVC_FUNCTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVC_FUNCTION
req.alt-loc: avc.h
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
---

# _tagAVC_FUNCTION enumeration



## -description
The AVC_FUNCTION enumeration type is used to specify AV/C subunit functions.



## -syntax

````
typedef enum _tagAVC_FUNCTION { 
  AVC_FUNCTION_COMMAND              = 0,
  AVC_FUNCTION_GET_PIN_COUNT        = 1,
  AVC_FUNCTION_GET_PIN_DESCRIPTOR   = 2,
  AVC_FUNCTION_GET_CONNECTINFO      = 3,
  AVC_FUNCTION_SET_CONNECTINFO      = 4,
  AVC_FUNCTION_ACQUIRE              = 5,
  AVC_FUNCTION_RELEASE              = 6,
  AVC_FUNCTION_CLR_CONNECTINFO      = 7,
  AVC_FUNCTION_GET_EXT_PLUG_COUNTS  = 8,
  AVC_FUNCTION_GET_UNIQUE_ID        = 9,
  AVC_FUNCTION_GET_REQUEST          = 10,
  AVC_FUNCTION_SEND_RESPONSE        = 11,
  AVC_FUNCTION_FIND_PEER_DO         = 12,
  AVC_FUNCTION_PEER_DO_LIST         = 13,
  AVC_FUNCTION_GET_SUBUNIT_INFO     = 14
} AVC_FUNCTION;
````


## -enum-fields

### -field AVC_FUNCTION_COMMAND

This value is a function code used to send an AV/C request and receive a response as one operation. This function code uses the AVC_COMMAND_IRB structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_PIN_COUNT

This value is a function code used to obtain the number of pins supported by the underlying subunit device. This function code uses the AVC_PIN_COUNT structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_PIN_DESCRIPTOR

This value is a function code used to obtain the pin descriptor for each pin ID. This function code uses the AVC_PIN_DESCRIPTOR structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_CONNECTINFO

This value is a function code used to obtain the AVCPRECONNECTINFO structure for each pin ID. This function code uses the AVC_PRE_CONNECTINFO structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_SET_CONNECTINFO

This value is a function code used to set the AVCCONNECTINFO structure for each pin ID. This function code uses the AVC_SET_CONNECTINFO structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_ACQUIRE

This value is a function code used to cause <i>avc.sys</i> to establish any connections suggested by cached AVCCONNECTINFO values. This function code uses the AVC_PIN_ID structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_RELEASE

This value is a function code used to cause <i>avc.sys</i> to release any connections suggested by cached AVCCONNECTINFO values. This function code uses the AVC_PIN_ID structure.


### -field AVC_FUNCTION_CLR_CONNECTINFO

This value is a function code used to cause <i>avc.sys</i> to remove any cached AVCCONNECTINFO values. This function code uses the AVC_PIN_ID structure. 

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_EXT_PLUG_COUNTS

This value is a function code used to cause <i>avc.sys</i> to obtain the external input and output plug counts. This function code uses the AVC_EXT_PLUG_COUNTS structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_UNIQUE_ID

This value is a function code used to obtain the unique ID of the AV/C unit. This function code uses the AVC_UNIQUE_ID structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_REQUEST

This value is a function code used to register to receive AV/C unit and subunit requests. This function code uses the AVC_COMMAND_IRB structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_SEND_RESPONSE

This value is a function code used to cause <i>avc.sys</i> to respond to AV/C unit and subunit requests. This function code uses the AVC_COMMAND_IRB structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_FIND_PEER_DO

This value is a function code used to locate a nonvirtual <i>avc.sys</i> instance. This function code uses the AVC_PEER_DO_LOCATOR structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_PEER_DO_LIST

This value is a function code used to locate all nonvirtual <i>avc.sys</i> instances. This function code uses the AVC_PEER_DO_LIST structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_SUBUNIT_INFO

This value is a function code used to obtain the subunit information of the target device. This function code uses the AVC_SUBUNIT_INFO_BLOCK structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Avc.h (include Avc.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.avc_irb">AVC_IRB</a>
</dt>
<dt>
<a href="stream.avc_command_irb">AVC_COMMAND_IRB</a>
</dt>
<dt>
<a href="stream.avc_pin_count">AVC_PIN_COUNT</a>
</dt>
<dt>
<a href="stream.avc_pin_descriptor">AVC_PIN_DESCRIPTOR</a>
</dt>
<dt>
<a href="stream.avc_preconnect_info">AVC_PRECONNECT_INFO</a>
</dt>
<dt>
<a href="stream.avc_setconnect_info">AVC_SETCONNECT_INFO</a>
</dt>
<dt>
<a href="stream.avc_pin_id">AVC_PIN_ID</a>
</dt>
<dt>
<a href="stream.avc_ext_plug_counts">AVC_EXT_PLUG_COUNTS</a>
</dt>
<dt>
<a href="stream.avc_unique_id">AVC_UNIQUE_ID</a>
</dt>
<dt>
<a href="stream.avc_peer_do_locator">AVC_PEER_DO_LOCATOR</a>
</dt>
<dt>
<a href="stream.avc_peer_do_list">AVC_PEER_DO_LIST</a>
</dt>
<dt>
<a href="stream.avc_subunit_info_block">AVC_SUBUNIT_INFO_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_FUNCTION enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

