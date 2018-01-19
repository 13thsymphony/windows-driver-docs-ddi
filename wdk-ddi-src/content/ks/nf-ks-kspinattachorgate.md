---
UID : NF:ks.KsPinAttachOrGate
title : KsPinAttachOrGate function
author : windows-driver-content
description : The KsPinAttachOrGate function connects Pin as an input to a previously initialized OR gate, and connects OrGate as an input to the relevant filter's AND gate.
old-location : stream\kspinattachorgate.htm
old-project : stream
ms.assetid : 14fb5b30-7169-4d8a-ad72-d0ee86da7f98
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsPinAttachOrGate
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsPinAttachOrGate
req.alt-loc : Ks.lib,Ks.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : PASSIVE_LEVEL (See Remarks section)
req.typenames : 
---


# KsPinAttachOrGate function
The<b> KsPinAttachOrGate</b> function connects <i>Pin</i> as an input to a previously initialized OR gate, and connects <i>OrGate</i> as an input to the relevant filter's AND gate.

## Syntax

````
void KsPinAttachOrGate(
  _In_     PKSPIN  Pin,
  _In_opt_ PKSGATE OrGate
);
````

## Parameters

`Pin`

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure to use an input to the OR gate.

`OrGate`

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure that is the previously initialized OR gate to connect to the relevant filter's AND gate. If this optional parameter is NULL, any <b>KSGATE</b> currently attached to the pin is detached.


## Return Value

None

## Remarks

To insert the gate, first call <a href="..\ks\nf-ks-ksgateinitializeor.md">KsGateInitializeOr</a>. Then call <b>KsPinAttachOrGate</b>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

Do not leave an unattached OR gate at filter creation time. Instead, create the OR gate later, for example  when the minidriver instantiates the pin.

<b>KsPinAttachOrGate </b>must be called at IRQL = PASSIVE_LEVEL before the pin in question leaves KSSTATE_STOP.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL (See Remarks section) |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\nf-ks-kspinattachandgate.md">KsPinAttachAndGate</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateinitializeor.md">KsGateInitializeOr</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinAttachOrGate function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>