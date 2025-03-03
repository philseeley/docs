|ID|Description|Paths|
|---|---|---|
 |environment-depth-belowSurface|Depth Below Surface| environment.depth.belowSurface|
 |environment-depth-belowKeel|Depth Below Keel| environment.depth.belowKeel|
 |environment-depth-belowTransducer|Depth Below Transducer| environment.depth.belowTransducer|
 |boat-speed-through-water|Speed Through Water| navigation.speedThroughWater|
 |navigation-speed-over-ground|Speed Over Ground| navigation.speedOverGround|
 |wind-speed-apparent|Wind Speed Apparent| environment.wind.speedApparent|
 |wind-speed-true|Wind Speed True| environment.wind.speedTrue|
 |wind-direction-true|Wind Direction True| environment.wind.directionTrue|
 |wind-rose|Wind Rose| environment.wind.angleApparent<br>environment.wind.angleTrueWater<br>environment.wind.speedApparent<br>environment.wind.speedTrue|
 |navigation-position|Position| navigation.position|
 |navigation-course-over-ground|Course Over Ground| navigation.courseOverGroundTrue|
 |environment-water-temperature|Water Temperature| environment.water.temperature|
 |environment-outside-relative-humidity|Outside Humidity| environment.outside.relativeHumidity|
 |environment-inside-relative-humidity|Inside Humidity| environment.inside.relativeHumidity|
 |autopilot-status|Autopilot Status| steering.autopilot.state<br>steering.autopilot.target.windAngleApparent<br>navigation.currentRoute.waypoints<br>steering.autopilot.target.headingTrue<br>steering.autopilot.target.headingMagnetic<br>navigation.magneticVariation|
 |boat-rudder-angle|Rudder Angle| steering.rudderAngle|
 |date-time|Date/Time| navigation.datetime|
 |navigation-xte|Cross Track Error| navigation.*.crossTrackError|
 |wind-speed-true-beaufort|Wind True Beaufort| environment.wind.speedTrue|
 |environment-set-and-drift|Set & Drift| environment.current|
 |navigation-heading-true|Heading| navigation.headingTrue|
 |navigation-next-point-distance|Next Point Distance| navigation.*.nextPoint.distance|
 |navigation-next-point-velocity-made-good|Next Point VMG| navigation.*.nextPoint.velocityMadeGood|
 |navigation-next-point-time-to-go|Next Point TTG| navigation.*.nextPoint.timeToGo|
 |boat-attitude-roll|Roll| navigation.attitude|
 |navigation-xte-delta|XTE Delta| navigation.*.crossTrackError|
 |wind-apparent-angle|Apparent Wind Angle| environment.wind.angleApparent|
 |navigation-magnetic-variation|Magnetic Variation| navigation.magneticVariation|
 |environment-outside-temperature|Outside Temperature| environment.outside.temperature|
 |environment-outside-pressure|Outside Pressure| environment.outside.pressure|
 |environment-sun|Sunlight| environment.sunlight.times.*|
 |environment-moon|Moon| environment.moon.*|
 |anchor-alarm|Anchor Alarm| navigation.position<br>navigation.anchor.*|
 |electrical-batteries|Batteries| electrical.batteries.*|
 |electrical-battery-voltage-meter|Volt Meter| electrical.batteries..voltage|
 |electrical-battery-voltage|Battery Voltage| electrical.batteries..voltage|
 |electrical-battery-current|Battery Current| electrical.batteries..current|
 |electrical-battery-temperature|Battery Temperature| electrical.batteries..temperature|
 |electrical-inverter-current|Inverter Current| electrical.inverters..dc.current|
 |electrical-solar-voltage|Solar Voltage| electrical.solar..voltage|
 |electrical-solar-current|Solar Current| electrical.solar..current|
 |propulsion-rpm|Engine RPM| propulsion..revolutions|
 |propulsion-temp|Engine Temp| propulsion..temperature|
 |propulsion-exhaust-temp|Engine Exhaust Temp| propulsion..exhaustTemperature|
 |propulsion-oil-pressure|Engine Oil Pressure| propulsion..oilPressure|
 |propulsion-fuel-rate|Fuel Rate| propulsion..fuel.rate|
 |tanks|Tanks| tanks.*|
 |tank-freshwater|Fresh Water| tanks.freshWater..currentLevel|
 |tank-wastewater|Grey Water| tanks.wasteWater..currentLevel|
 |tank-blackwater|Black Water| tanks.blackWater..currentLevel|
 |tank-fuel|Fuel| tanks.fuel..currentLevel|
 |tank-lubrication|Lubrication| tanks.lubrication..currentLevel|
 |navigation-rate-of-turn|Rate of Turn| navigation.rateOfTurn|
 |electrical-switches|Switches| electrical.switches.*|
 |electrical-switch|Switch| electrical.switches..*|
 |rpi-cpu-temperature|RPi CPU Temperature| environment.rpi.cpu.temperature|
 |rpi-gpu-temperature|RPi GPU Temperature| environment.rpi.gpu.temperature|
 |rpi-cpu-utilisation|RPi CPU Utilisation| environment.rpi.cpu.utilisation|
 |rpi-memory-utilisation|RPi Memory Utilisation| environment.rpi.memory.utilisation|
 |rpi-sd-utilisation|RPi SD Utilisation| environment.rpi.sd.utilisation|
 |rpi|Raspberry Pi| environment.rpi.*|
