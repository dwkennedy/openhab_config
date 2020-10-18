# openhab_config
Configuration files for my openhab2 setup

The good stuff is in rules and items (to be placed in /etc/openhab2/rules, /etc/openhab2/items)

items:
  astro.items: creates objects to hold calculated times for sunrise, sunset, etc.  Also vTimeOfDay, which is a handy variable to check to see what daypart we are currently in (DAY=sunrise to sunset, NIGHT= after sunset to 10PM, BED=10pm to sunrise, roughly)
  
rules:
  timeofday.rules:  calculates and publishes the times that DAY, NIGHT, BED, etc. start.  publishes the vTimeOfDay variable, which holds DAY, NIGHT, or BED based on the current time.  This logic could be extended for weekends, holidays, or adding additional day parts (TEA_TIME?)
  nightlight.rules: turns on front light at NIGHT, off(motion-only) at BED, then off during DAY
  front_motion.rules: turn on light when motion detected, turn off after sensor reports no motions (factory default 4 minutes)
  
Using AEOTEC MultiSensor6, AEOTEC gen 5 z-wave stick, and tplink kasa switches

The user might turn the light on/off manually.  after DAY is over, the motion will still trigger ON (and then OFF after the timer expires)  This may not be what is desired, maybe if the light is on after BED for some reason it should be left on?
  
  
