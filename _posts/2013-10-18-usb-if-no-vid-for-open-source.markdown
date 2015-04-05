---
layout: disquspost
title: "usb-if: No VID for open source"
date: 2013-10-18 22:24
comments: true
categories: usb
---

By now, you're probably aware that every compliant USB device requires a Vendor ID (VID) and Product ID (PID), and that VIDs are handed out - in return for substantial monetary compensation - exclusively by the USB-IF. This has proven problematic for open source hobbyists and small electronics businesses for a long time, since the fees they demand are well outside what's affordable for a small project or a hobby. I've had a pet theory on how to resolve this for a while, though, and recently I decided to see if it could really work.

My idea was this: While USB-IF prohibits resale of PIDs, they don't - or at least didn't until recently, see below - prohibit handing out PIDs for limited use for free, as witnessed by organisations like Microchip and FTDI who hand out PIDs for use on their hardware, or by OpenMoko, who hand out PIDs on their VID to open source users. Therefore, perhaps a not-for-profit foundation could be formed, solicit donations for a VID, and hand out PIDs free of charge to anyone who meets the criteria. Such a foundation could also reserve a few PIDs for 'generic' devices that expose a well defined set of endpoints, enabling drivers for such to be produced and qualified with MS.

I decided to see if this was as practical as I thought it would be. Unfortunately, USB-IF have recently increased their fee to $5000 US, and updated their [Vendor ID agreement](http://www.usb.org/developers/vendor/VID_Only_Form_withCCAuth_010113.pdf)(PDF) to include the following text:

>    The company set forth above hereby applies for a USB Vendor ID Number and agrees to the following: The USB Implementers Forum is the authority which assigns and maintains all USB Vendor ID Numbers. Each Vendor ID Number is assigned to one company for its sole and exclusive use, along with associated Product ID Numbers. They may not be sold, transferred, or used by others, directly or indirectly, except in special circumstances, and then only upon prior written approval by USB-IF. Unauthorized use of assigned or unassigned USB Vendor ID Numbers and associated Product ID Numbers are strictly prohibited.

Not great - but there's still that "special circumstances" and "prior written approval" bit. So I sent the USB-IF a very polite letter enquiring about the possibility:

>    Hi,
>
>    I'm interested in licensing a VID from the USB-IF explicitly for the purpose of enabling small developers producing open source hardware to more easily produce USB devices.
>
>    Tentatively, this would involve establishing a not for profit foundation, whose members are allocated PIDs from a VID owned by the foundation. Membership would be free of charge, and PIDs would not be charged for either. PIDs would not be available to anyone outside the foundation, or anyone producing hardware that is not open source; if needed additional restrictions on number of units could be imposed. These amount to similar or more restrictive terms as those followed by FTDI and Microchip, who provide PIDs to users of their hardware.
>
>    Are you prepared to license a VID along these lines? A great deal of the open source and OSHW community would benefit from being able to more easily produce USB devices on a small scale, one not currently catered for by the issuing of VIDs to larger organisations.
>
>    Regards,
>
>    Nick Johnson
>
>    Director
>
>    Arachnid Labs Ltd

A few hours later, I got a response:

>    Dear Nick,
>     
>    Thank you for your message. The USB VID is the property of the USB Implementers Forum (“USB-IF”) and is assigned by the USB-IF for use solely by the original vendor to whom the VID is issued. The VID is provided to the assigned company to identify only its own products and neither the VID nor associated PIDs may be sublicensed, transferred or offered for resale in any manner.
>    
>    The policy of the USB-IF regarding vendor ID numbers (VIDs) is as stated in the [attached policy statement](/assets/VIDPIDPolicyv2.pdf). In general, VIDs are not transferable.
>   
>    The USB-IF has long had a VID/PID process for hobbyists.
>     
>    Please immediately cease and desist raising funds to purchase a unique USB VID for the purpose of transferring, reselling or sublicensing PIDs and delete all references to the USB-IF, VIDs and PIDs for transfer, resale or sublicense from your website and other marketing materials.
>     
>    Please kindly reply no later than Friday, October 25 with your written assurance that you will no longer promote the purchase of a community VID or PIDs for sale, transfer, or use by a third party.
>     
>    Best regards,
>
>    Traci Donnell
>
>    Executive Director

I'll leave it to you to judge if that seems proportional. Regardless, the message is clear: No VIDs for you.

If anyone knows what the USB-IF's VID/PID process for hobbyists is, I'd like to hear it. I'll ask them for details and update this post if I receive one.

Update: USB-IF's response about the 'hobbyist process':

> Hi Nick,
>  
> We do have a vendor ID number designated for prototype products. This vendor ID number may not be used for a production product. Anybody who has such a need may contact us directly and we will provide them with the proto VID once they confirm that will not be making production products to be distributed and/or sold in the marketplace.
> 
> Best regards,
> Traci

Interesting to know - I'd certainly never heard that this was an option - but it doesn't seem to be a practical option for those of us who sell our gear in small quantities, but it might work if you want to publish your design as OSHW for other people to build themselves.
