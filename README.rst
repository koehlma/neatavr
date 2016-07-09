NeatAVR
=======
NeatAVR is an experimental library for AVR microchips based on C++ meta programming.


Example
-------

.. code:: javascript

    #define F_CPU 8000000UL

    #include "neatavr.hpp"

    #include "neatavr/serial.hpp"

    #include <util/delay.h>

    using namespace NeatAVR;

    typedef Arduino13 LED;

    int main() {
        Serial::init();

        Serial::printline("Hello World!");

        LED::output();

        System::enable_interrupts();

        while (1) {
            _delay_ms(500);

            LED::toggle()
        }
    }