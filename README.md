CPPNotifications
================

C++ Notification System
-----------------------

Copyright (c) 2012, Jean-David Gadina <macmade@eosgarden.com>  
Distributed under the Boost Software License, Version 1.0.

### About:

CPPNotifications is a Cocoa like (Objective-C) notification system for C++ (POSIX and Windows).

### License:

CPPNotifications is released under the terms of the [Boost][1] Software License - Version 1.0.

[1]: http://www.boost.org/LICENSE_1_0.txt   "BOOST"

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
