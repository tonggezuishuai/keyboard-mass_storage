# Use For Linux USB Gadget Composite Device 
HID keyboard + Mass storage   
base on /linux/drivers/usb/gadget/acm_ms.c  
  
After patched,we can see the information of usb tree viewer.There are two devices. If you want more,please push your question here.  

   ---------------------- Device Descriptor ----------------------  
bLength                  : 0x12 (18 bytes)  
bDescriptorType          : 0x01 (Device Descriptor)  
bcdUSB                   : 0x200 (USB Version 2.00)  
bDeviceClass             : 0xEF (Miscellaneous)  
bDeviceSubClass          : 0x02
bDeviceProtocol          : 0x01 (IAD - Interface Association Descriptor)  
bMaxPacketSize0          : 0x40 (64 bytes)  
idVendor                 : 0x2345 (ZOWIE GEAR)  
idProduct                : 0x5432  
bcdDevice                : 0x0310  
iManufacturer            : 0x02 (String Descriptor 2)  
 Language 0x0409         : "Linux 3.10.49 with dwc_otg_pcd"  
iProduct                 : 0x03 (String Descriptor 3)  
 Language 0x0409         : "Composite Gadget (HID + MS)"  
iSerialNumber            : 0x00 (No String Descriptor)  
bNumConfigurations       : 0x01 (1 Configuration)  
Data (HexDump)           : 12 01 00 02 EF 02 01 40 45 23 32 54 10 03 02 03   .......@E#2T....  
                           00 01                                             ..  

    ------------------ Configuration Descriptor -------------------
bLength                  : 0x09 (9 bytes)  
bDescriptorType          : 0x02 (Configuration Descriptor)  
wTotalLength             : 0x0040 (64 bytes)  
bNumInterfaces           : 0x02 (2 Interfaces)  
bConfigurationValue      : 0x01 (Configuration 1)  
iConfiguration           : 0x00 (No String Descriptor)  
bmAttributes             : 0xC0  
 D7: Reserved, set 1     : 0x01  
 D6: Self Powered        : 0x01 (yes)  
 D5: Remote Wakeup       : 0x00 (no)  
 D4..0: Reserved, set 0  : 0x00  
MaxPower                 : 0x01 (2 mA)  
Data (HexDump)           : 09 02 40 00 02 01 00 C0 01 09 04 00 00 02 03 00   ..@.............  
                           01 05 09 21 01 01 00 01 22 3F 00 07 05 81 03 08   ...!...."?......  
                           00 04 07 05 02 03 08 00 04 09 04 01 00 02 08 06   ................  
                           50 01 07 05 83 02 00 02 00 07 05 04 02 00 02 01   P...............  

        ---------------- Interface Descriptor -----------------
bLength                  : 0x09 (9 bytes)  
bDescriptorType          : 0x04 (Interface Descriptor)  
bInterfaceNumber         : 0x00  
bAlternateSetting        : 0x00  
bNumEndpoints            : 0x02 (2 Endpoints)  
bInterfaceClass          : 0x03 (HID - Human Interface Device)  
bInterfaceSubClass       : 0x00 (None)  
bInterfaceProtocol       : 0x01 (Keyboard)  
iInterface               : 0x05 (String Descriptor 5)  
 Language 0x0409         : "HID Interface"  
Data (HexDump)           : 09 04 00 00 02 03 00 01 05                        .........  
 
        ------------------- HID Descriptor --------------------
bLength                  : 0x09 (9 bytes) 
bDescriptorType          : 0x21 (HID Descriptor)  
bcdHID                   : 0x0101 (HID Version 1.01)  
bCountryCode             : 0x00 (00 = not localized)  
bNumDescriptors          : 0x01 
Data (HexDump)           : 09 21 01 01 00 01 22 3F 00                        .!...."?.  
Descriptor 1:
bDescriptorType          : 0x22 (Class=Report)  
wDescriptorLength        : 0x003F (63 bytes) 
Error reading descriptor : ERROR_INVALID_PARAMETER (due to a obscure limitation of the Win32 USB API, see UsbTreeView.txt)  

        ----------------- Endpoint Descriptor -----------------
bLength                  : 0x07 (7 bytes)  
bDescriptorType          : 0x05 (Endpoint Descriptor)  
bEndpointAddress         : 0x81 (Direction=IN EndpointID=1)  
bmAttributes             : 0x03 (TransferType=Interrupt)  
wMaxPacketSize           : 0x0008  
 Bits 15..13             : 0x00 (reserved, must be zero)  
 Bits 12..11             : 0x00 (0 additional transactions per microframe -> allows 1..1024 bytes per packet)  
 Bits 10..0              : 0x08 (8 bytes per packet)  
bInterval                : 0x04 (4 ms)  
Data (HexDump)           : 07 05 81 03 08 00 04                              .......  

        ----------------- Endpoint Descriptor -----------------
bLength                  : 0x07 (7 bytes)  
bDescriptorType          : 0x05 (Endpoint Descriptor)  
bEndpointAddress         : 0x02 (Direction=OUT EndpointID=2)  
bmAttributes             : 0x03 (TransferType=Interrupt)  
wMaxPacketSize           : 0x0008  
 Bits 15..13             : 0x00 (reserved, must be zero)  
 Bits 12..11             : 0x00 (0 additional transactions per microframe -> allows 1..1024 bytes per packet)  
 Bits 10..0              : 0x08 (8 bytes per packet)  
bInterval                : 0x04 (4 ms)  
Data (HexDump)           : 07 05 02 03 08 00 04                              .......  

        ---------------- Interface Descriptor -----------------
bLength                  : 0x09 (9 bytes)  
bDescriptorType          : 0x04 (Interface Descriptor)  
bInterfaceNumber         : 0x01  
bAlternateSetting        : 0x00  
bNumEndpoints            : 0x02 (2 Endpoints)  
bInterfaceClass          : 0x08 (Mass Storage)  
bInterfaceSubClass       : 0x06 (SCSI transparent command set)  
bInterfaceProtocol       : 0x50 (Bulk-Only Transport)  
iInterface               : 0x01 (String Descriptor 1)  
 Language 0x0409         : "Mass Storage"  
Data (HexDump)           : 09 04 01 00 02 08 06 50 01                        .......P.  

        ----------------- Endpoint Descriptor -----------------
bLength                  : 0x07 (7 bytes)  
bDescriptorType          : 0x05 (Endpoint Descriptor)  
bEndpointAddress         : 0x83 (Direction=IN EndpointID=3)  
bmAttributes             : 0x02 (TransferType=Bulk)  
wMaxPacketSize           : 0x0200 (max 512 bytes)  
bInterval                : 0x00 (never NAKs)  
Data (HexDump)           : 07 05 83 02 00 02 00                              .......  

        ----------------- Endpoint Descriptor -----------------
bLength                  : 0x07 (7 bytes)  
bDescriptorType          : 0x05 (Endpoint Descriptor)  
bEndpointAddress         : 0x04 (Direction=OUT EndpointID=4)  
bmAttributes             : 0x02 (TransferType=Bulk)  
wMaxPacketSize           : 0x0200 (max 512 bytes)  
bInterval                : 0x01 (at most 1 NAK each 1 microframes)  
Data (HexDump)           : 07 05 04 02 00 02 01                              .......  

    ----------------- Device Qualifier Descriptor -----------------
bLength                  : 0x0A (10 bytes)  
bDescriptorType          : 0x06 (Device_qualifier Descriptor)  
bcdUSB                   : 0x200 (USB Version 2.00)  
bDeviceClass             : 0xEF (Miscellaneous)  
bDeviceSubClass          : 0x02  
bDeviceProtocol          : 0x01 (IAD - Interface Association Descriptor)  
bMaxPacketSize0          : 0x40 (64 Bytes)  
bNumConfigurations       : 0x01 (1 other-speed configuration)  
bReserved                : 0x00  
Data (HexDump)           : 0A 06 00 02 EF 02 01 40 01 00                     .......@..  


