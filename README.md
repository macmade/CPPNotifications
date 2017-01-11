CPPNotifications
================

[![Build Status](https://img.shields.io/travis/macmade/CPPNotifications.svg?branch=master&style=flat)](https://travis-ci.org/macmade/CPPNotifications)
[![Issues](http://img.shields.io/github/issues/macmade/CPPNotifications.svg?style=flat)](https://github.com/macmade/CPPNotifications/issues)
![Status](https://img.shields.io/badge/status-inactive-lightgray.svg?style=flat)
![License](https://img.shields.io/badge/license-boost-brightgreen.svg?style=flat)
[![Contact](https://img.shields.io/badge/contact-@macmade-blue.svg?style=flat)](https://twitter.com/macmade)  
[![Donate-Patreon](https://img.shields.io/badge/donate-patreon-yellow.svg?style=flat)](https://patreon.com/macmade)
[![Donate-Gratipay](https://img.shields.io/badge/donate-gratipay-yellow.svg?style=flat)](https://www.gratipay.com/macmade)
[![Donate-Paypal](https://img.shields.io/badge/donate-paypal-yellow.svg?style=flat)](https://paypal.me/xslabs)

About
-----

**C++ Notification System**  
CPPNotifications is a Cocoa like (Objective-C) notification system for C++ (POSIX and Windows).

Documentation
-------------

### Example:

    #include <iostream>
    #include "NotificationCenter.h"
    
    class Bar: public EOS::Observer
    {
        public:
            
            void handleNotification( const EOS::Notification & );
    };
    
    void Bar::handleNotification( const EOS::Notification & notification )
    {
        std::cout << "Received notification: " << notification.name() << std::endl;
    }
    
    int main( void )
    {
        Bar b1;
        Bar b2;
        
        EOS::NotificationCenter::defaultCenter().addObserver( b1, "test" );
        EOS::NotificationCenter::defaultCenter().addObserver( b2, "test" );
        EOS::NotificationCenter::defaultCenter().postNotification( "test" );
        
        return 0;
    }

License
-------

CPPNotifications is released under the terms of the Boost Software License - Version 1.0.

Repository Infos
----------------

    Owner:			Jean-David Gadina - XS-Labs
    Web:			www.xs-labs.com
    Blog:			www.noxeos.com
    Twitter:		@macmade
    GitHub:			github.com/macmade
    LinkedIn:		ch.linkedin.com/in/macmade/
    StackOverflow:	stackoverflow.com/users/182676/macmade
