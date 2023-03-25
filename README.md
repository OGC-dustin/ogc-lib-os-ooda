# OGC.Engineering
## ogc-lib-os-ooda - Observe, Orient, Decide, Act
Developer contact - dustin < at > ogc.engineering

---
https://en.wikipedia.org/wiki/OODA_loop

The OODA loop is the cycle observe–>orient–>decide–>act, developed by military
strategist and United States Air Force Colonel John Boyd.  Focused on agility,
the OODA loop takes whatever data is available at the time to make decisions and
adapt to changes.

---
* Observe:
* Orient:
* Decide:
* Act:

Library provides main function with general system initialization functions and
main loop to cycle through observe–>orient–>decide–>act function calls.

---
Requirements:

---

- the DEPLOYMENT/PROJECT layer(folder) must contain:
    - app.h header that redirects to the primary application ( because multiple applications are possible )

- the APP layer(folder) must define:
    - void app_init( void );
        - The function app_init() must initialize any data needed before starting the OODA cycle function calls
        - It is expected that each function will track its own state or global structures will track said state
    - void observe( void );
    - void orient( void );
    - void decide( void );
    - void act( void );

- the HAL layer(folder) must define:
    - void hal_config ( void );
        - configuration of the watchdog, clocks, pins, and other things that do not require the scheduler
    - void hal_init( void );
        - initialization of hal level nrtps tasks that need the scheduler ( i.e. background tasks )
