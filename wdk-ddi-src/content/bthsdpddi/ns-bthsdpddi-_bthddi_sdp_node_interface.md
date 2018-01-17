---
UID: NS:bthsdpddi._BTHDDI_SDP_NODE_INTERFACE
title: _BTHDDI_SDP_NODE_INTERFACE
author: windows-driver-content
description: The BTHDDI_SDP_NODE_INTERFACE structure provides functions for manipulating SDP records, including converting them to and from a tree representation that profile drivers can more easily parse.
old-location: bltooth\bthddi_sdp_node_interface.htm
old-project: bltooth
ms.assetid: c9aeaaed-f017-4b23-b867-d704c4f8afb6
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _BTHDDI_SDP_NODE_INTERFACE, BTHDDI_SDP_NODE_INTERFACE, *PBTHDDI_SDP_NODE_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BTHDDI_SDP_NODE_INTERFACE
req.alt-loc: bthsdpddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.typenames: BTHDDI_SDP_NODE_INTERFACE, *PBTHDDI_SDP_NODE_INTERFACE
---

# _BTHDDI_SDP_NODE_INTERFACE structure



## -description
The BTHDDI_SDP_NODE_INTERFACE structure provides functions for manipulating SDP records, including
  converting them to and from a tree representation that profile drivers can more easily parse.



## -syntax

````
typedef struct _BTHDDI_SDP_NODE_INTERFACE {
  INTERFACE                  Interface;
  PCREATENODETREEROOT        SdpCreateNodeTree;
  PFREETREE                  SdpFreeTree;
  PCREATENODENIL             SdpCreateNodeNil;
  PCREATENODEBOOLEAN         SdpCreateNodeBoolean;
  PCREATENODEUINT8           SdpCreateNodeUint8;
  PCREATENODEUINT16          SdpCreateNodeUint16;
  PCREATENODEUINT32          SdpCreateNodeUint32;
  PCREATENODEUINT64          SdpCreateNodeUint64;
  PCREATENODEUINT128         SdpCreateNodeUint128;
  PCREATENODEINT8            SdpCreateNodeInt8;
  PCREATENODEINT16           SdpCreateNodeInt16;
  PCREATENODEINT32           SdpCreateNodeInt32;
  PCREATENODEINT64           SdpCreateNodeInt64;
  PCREATENODEINT128          SdpCreateNodeInt128;
  PCREATENODEUUID16          SdpCreateNodeUuid16;
  PCREATENODEUUID32          SdpCreateNodeUuid32;
  PCREATENODEUUID128         SdpCreateNodeUuid128;
  PCREATENODESTRING          SdpCreateNodeString;
  PCREATENODEURL             SdpCreateNodeUrl;
  PCREATENODEALTERNATIVE     SdpCreateNodeAlternative;
  PCREATENODESEQUENCE        SdpCreateNodeSequence;
  PADDATTRIBUTETOTREEE       SdpAddAttributeToTree;
  PAPPENDNODETOCONTAINERNODE SdpAppendNodeToContainerNode;
} BTHDDI_SDP_NODE_INTERFACE, *PBTHDDI_SDP_NODE_INTERFACE;
````


## -struct-fields

### -field Interface

A structure that describes the 
     <b>BTHDDI_SDP_NODE_INTERFACE</b> interface for use by profile drivers. For more information about this
     structure, see 
     <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>.


### -field SdpCreateNodeTree

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodetree.md">SdpCreateNodeTree</a> function.


### -field SdpFreeTree

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpfreetree.md">SdpFreeTree</a> function
     <i>.</i>


### -field SdpCreateNodeNil

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodenil.md">SdpCreateNodeNil</a> function.


### -field SdpCreateNodeBoolean

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeboolean.md">SdpCreateNodeBoolean</a> function.


### -field SdpCreateNodeUint8

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeuint8.md">SdpCreateNodeUInt8</a> function.


### -field SdpCreateNodeUint16

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeuint16.md">SdpCreateNodeUInt16</a> function.


### -field SdpCreateNodeUint32

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeuint32.md">SdpCreateNodeUInt32</a> function.


### -field SdpCreateNodeUint64

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeuint64.md">SdpCreateNodeUInt64</a> function.


### -field SdpCreateNodeUint128

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeuint128.md">SdpCreateNodeUInt128</a> function.


### -field SdpCreateNodeInt8

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeuint128.md">SdpCreateNodeInt8</a> function.


### -field SdpCreateNodeInt16

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeint16.md">SdpCreateNodeInt16</a> function.


### -field SdpCreateNodeInt32

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeint32.md">SdpCreateNodeInt32</a> function.


### -field SdpCreateNodeInt64

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeint64.md">SdpCreateNodeInt64</a> function.


### -field SdpCreateNodeInt128

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeint128.md">SdpCreateNodeInt128</a> function.


### -field SdpCreateNodeUuid16

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeuuid16.md">SdpCreateNodeUUID16</a> function.


### -field SdpCreateNodeUuid32

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeuuid32.md">SdpCreateNodeUUID32</a> function.


### -field SdpCreateNodeUuid128

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeuuid128.md">SdpCreateNodeUUID128</a> function.


### -field SdpCreateNodeString

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodestring.md">SdpCreateNodeString</a> function.


### -field SdpCreateNodeUrl

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodeurl.md">SdpCreateNodeUrl</a> function.


### -field SdpCreateNodeAlternative

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodealternative.md">
     SdpCreateNodeAlternative</a> function.


### -field SdpCreateNodeSequence

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpcreatenodesequence.md">
     SdpCreateNodeSequence</a> function.


### -field SdpAddAttributeToTree

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">
     SdpAddAttributeToTree</a> function.


### -field SdpAppendNodeToContainerNode

A pointer to the 
     <a href="..\sdplib\nf-sdplib-sdpappendnodetocontainernode.md">
     SdpAppendNodeToContainerNode</a> function.


## -remarks
Profile drivers should specify the 
    <b>GUID_BTHDDI_SDP_NODE_INTERFACE</b> GUID to query for an instance of the BTHDDI_SDP_NODE_INTERFACE
    structure from the Bluetooth driver stack.

All the members of this structure, other than the 
    <b>Interface</b> member, are function pointers.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodetree.md">SdpCreateNodeTree</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpfreetree.md">SdpFreeTree</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodenil.md">SdpCreateNodeNil</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeboolean.md">SdpCreateNodeBoolean</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeuint8.md">SdpCreateNodeUInt8</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeuint16.md">SdpCreateNodeUInt16</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeuint32.md">SdpCreateNodeUInt32</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeuint64.md">SdpCreateNodeUInt64</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeuint128.md">SdpCreateNodeUInt128</a>
</dt>
<dt><b>SdpCreateNodeInt8</b></dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeint16.md">SdpCreateNodeInt16</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeint32.md">SdpCreateNodeInt32</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeint64.md">SdpCreateNodeInt64</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeint128.md">SdpCreateNodeInt128</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeuuid16.md">SdpCreateNodeUUID16</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeuuid32.md">SdpCreateNodeUUID32</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeuuid128.md">SdpCreateNodeUUID128</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodestring.md">SdpCreateNodeString</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodeurl.md">SdpCreateNodeUrl</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodealternative.md">SdpCreateNodeAlternative</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpcreatenodesequence.md">SdpCreateNodeSequence</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpaddattributetotree.md">SdpAddAttributeToTree</a>
</dt>
<dt>
<a href="..\sdplib\nf-sdplib-sdpappendnodetocontainernode.md">SdpAppendNodeToContainerNode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTHDDI_SDP_NODE_INTERFACE structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

