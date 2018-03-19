---
UID: NE:usb._USB_CONTROLLER_FLAVOR
title: "_USB_CONTROLLER_FLAVOR"
author: windows-driver-content
description: The USB_CONTROLLER_FLAVOR enumeration specifies the type of USB host controller.
old-location: buses\usb_controller_flavor.htm
old-project: usbref
ms.assetid: c732fe90-50fb-4f6e-b42e-cb35c1ed0091
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EHCI_Generic, EHCI_Intel_Medfield, EHCI_Lucent, EHCI_NEC, EHCI_NVIDIA_Tegra2, EHCI_NVIDIA_Tegra3, OHCI_Generic, OHCI_Hydra, OHCI_NEC, UHCI_Generic, UHCI_Ich1, UHCI_Ich2, UHCI_Ich3m, UHCI_Ich4, UHCI_Ich5, UHCI_Ich6, UHCI_Intel, UHCI_Piix3, UHCI_Piix4, UHCI_VIA, UHCI_VIA_x01, UHCI_VIA_x02, UHCI_VIA_x03, UHCI_VIA_x04, UHCI_VIA_x0E_FIFO, USB_CONTROLLER_FLAVOR, USB_CONTROLLER_FLAVOR enumeration [Buses], USB_HcGeneric, _USB_CONTROLLER_FLAVOR, buses.usb_controller_flavor, usb/EHCI_Generic, usb/EHCI_Intel_Medfield, usb/EHCI_Lucent, usb/EHCI_NEC, usb/EHCI_NVIDIA_Tegra2, usb/EHCI_NVIDIA_Tegra3, usb/OHCI_Generic, usb/OHCI_Hydra, usb/OHCI_NEC, usb/UHCI_Generic, usb/UHCI_Ich1, usb/UHCI_Ich2, usb/UHCI_Ich3m, usb/UHCI_Ich4, usb/UHCI_Ich5, usb/UHCI_Ich6, usb/UHCI_Intel, usb/UHCI_Piix3, usb/UHCI_Piix4, usb/UHCI_VIA, usb/UHCI_VIA_x01, usb/UHCI_VIA_x02, usb/UHCI_VIA_x03, usb/UHCI_VIA_x04, usb/UHCI_VIA_x0E_FIFO, usb/USB_CONTROLLER_FLAVOR, usb/USB_HcGeneric, usbstrct_a1b79c0b-7ee4-48bd-9793-8f37b9d248f2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usb.h
api_name:
-	USB_CONTROLLER_FLAVOR
product: Windows
targetos: Windows
req.typenames: USB_CONTROLLER_FLAVOR
req.product: Windows 10 or later.
---

# _USB_CONTROLLER_FLAVOR Enumeration
The <b>USB_CONTROLLER_FLAVOR</b> enumeration specifies the type of USB host controller.

## Syntax
````
typedef enum _USB_CONTROLLER_FLAVOR { 
  USB_HcGeneric        = 0,
  OHCI_Generic         = 100,
  OHCI_Hydra           = 101,
  OHCI_NEC             = 102,
  UHCI_Generic         = 200,
  UHCI_Piix4           = 201,
  UHCI_Piix3           = 202,
  UHCI_Ich2            = 203,
  UHCI_Ich1            = 205,
  UHCI_Ich3m           = 206,
  UHCI_Ich4            = 207,
  UHCI_Ich5            = 208,
  UHCI_Ich6            = 209,
  UHCI_Intel           = 249,
  UHCI_VIA             = 250,
  UHCI_VIA_x01         = 251,
  UHCI_VIA_x02         = 252,
  UHCI_VIA_x03         = 253,
  UHCI_VIA_x04         = 254,
  UHCI_VIA_x0E_FIFO    = 264,
  EHCI_Generic         = 1000,
  EHCI_NEC             = 2000,
  EHCI_Lucent          = 3000,
  EHCI_NVIDIA_Tegra2   = 4000,
  EHCI_NVIDIA_Tegra3   = 4001,
  EHCI_Intel_Medfield  = 5001
} USB_CONTROLLER_FLAVOR;
````

## Constants

<table>
            
                <tr>
                    <td>USB_HcGeneric</td>
                    <td>Indicates a generic host controller.</td>
                </tr>
            
                <tr>
                    <td>OHCI_Generic</td>
                    <td>Indicates a generic OHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>OHCI_Hydra</td>
                    <td>Indicates a Hydra host controller.</td>
                </tr>
            
                <tr>
                    <td>OHCI_NEC</td>
                    <td>Indicates a NEC host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_Generic</td>
                    <td>Indicates a generic UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_Piix4</td>
                    <td>Indicates an Intel PIIX4 UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_Piix3</td>
                    <td>Indicates an Intel PIIX3 UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_Ich2</td>
                    <td>Indicates an Intel ICH2 UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_Reserved204</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>UHCI_Ich1</td>
                    <td>Indicates an Intel 815 ICH1 UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_Ich3m</td>
                    <td>Indicates an Intel ICH3m UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_Ich4</td>
                    <td>Indicates an Intel ICH4m UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_Ich5</td>
                    <td>Indicates an Intel ICH5m UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_Ich6</td>
                    <td>Indicates an Intel ICH6m UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_Intel</td>
                    <td>Indicates a generic Intel UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_VIA</td>
                    <td>Indicates a generic VIA UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_VIA_x01</td>
                    <td>Indicates a Revision 1 VIA UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_VIA_x02</td>
                    <td>Indicates a Revision 2 VIA UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_VIA_x03</td>
                    <td>Indicates a Revision 3 VIA UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_VIA_x04</td>
                    <td>Indicates a Revision 4 VIA UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UHCI_VIA_x0E_FIFO</td>
                    <td>Indicates a FIFO Revision VIA UHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>EHCI_Generic</td>
                    <td>Indicates a generic EHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>EHCI_NEC</td>
                    <td>Indicates an NEC EHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>EHCI_Lucent</td>
                    <td>Indicates an EHCI Lucent host controller.</td>
                </tr>
            
                <tr>
                    <td>EHCI_NVIDIA_Tegra2</td>
                    <td>Indicates a Revision 2 NVIDIA Tegra EHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>EHCI_NVIDIA_Tegra3</td>
                    <td>Indicates a Revision 3 NVIDIA Tegra EHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>EHCI_Intel_Medfield</td>
                    <td>Indicates an Intel Medfield host controller.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usb.h (include Usb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539256">USB_CONTROLLER_INFO_0</a>