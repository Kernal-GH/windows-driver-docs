---
title: Joystick Support
author: windows-driver-content
description: Joystick Support
MS-HAID:
- 'di\_4a6d7425-64f3-4d3e-bbb0-c19ba70d910e.xml'
- 'hid.joystick\_support'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 09fcbdf0-4e70-4144-9afc-4b085a2b4ba7
keywords: ["joysticks WDK HID", "joysticks WDK HID , about joysticks", "minidrivers WDK joysticks", "virtual joystick drivers WDK HID", "VJoyD WDK HID", "virtual joystick drivers WDK HID , about VJoyD", "VJoyD WDK HID , about VJoyD"]
---

# Joystick Support


## <a href="" id="ddk-joystick-support-di"></a>


There are differences from version to version in the type of joystick support that Microsoft DirectX offers. In Windows 95/98/Me, DirectX supports two methods to customize joystick capabilities: through custom entries in the Windows registry and through a virtual device driver (VxD) creation, which is called as *joystick minidriver*. The minidrivers that are used in DirectX versions 1.0, 2.0, and 3.0 support the original minidriver interface, with minor differences in the DirectX 3.0 interface. In addition to the original minidriver model, DirectX versions 5.0, and later, include an alternative driver interface that is generally described separately.

Windows 95/98/Me joystick driver and configuration programs support analog joysticks that plug into the IBM standard game port. Joystick makers can make the joystick configuration programs customizable and provide explicit directions to the end user on how to customize the joystick. Joysticks can signal Windows 95/98/Me about their capabilities through the registry. These capabilities can include the use of throttle, point-of-view (POV) hats, rudders, and the number of joystick buttons.

All non-IBM standard joysticks, such as digital joysticks, MIDI joysticks, and analog joysticks driven by joystick accelerators must provide a joystick minidriver in addition to custom registry information. A joystick OEM can write a minidriver that provides access to nonstandard joystick hardware. This provides a mechanism for digital joysticks to work with any Windows-based game that uses the joystick application programming interface (API).

The driver model can deal with up to six axes, a POV hat, and a double word of buttons, so that an OEM can easily create a minidriver for new hardware with a higher degree of freedom than the current game port allows. The joystick minidriver provides complete flexibility to hardware vendors and allows game creators to use the installed base with their titles. In DirectX 5.0 and later, analog joystick support is also separated into a minidriver that uses a new interface. This new interface is loaded only when an analog game port is configured. The polling is extended with three extra POV hats, three more double words that contains button data, and a method to specify that it returns the velocity, acceleration, and/or force data for each axis.

The current virtual joystick driver (VJoyD) allows the configuration of up to 16 devices, any number of which can be driven by minidrivers. The configuration of minidrivers to devices can be one to one or one to many.

This section includes:

[Joystick Driver Model](joystick-driver-model.md)

[Minidriver-Supplied Callbacks](minidriver-supplied-callbacks.md)

[Original Interface](original-interface.md)

[DirectX 5.0 Interface](directx-5-0-interface.md)

[INF File Creation](creating-an-inf-file.md)

[Registry Settings](registry-settings2.md)

[VJoyD Minidriver Override](vjoyd-minidriver-override.md)

[Axis Selection](axis-selection.md)

 

 


--------------------
[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bhid\hid%5D:%20Joystick%20Support%20%20RELEASE:%20%287/18/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")


