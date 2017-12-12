# STM32RTC
A RTC library for STM32.

# API

This library is based on the Arduino RTCZero library.
You can take control of the internal RTC of the STM32 boards.

The following functions are not supported:

* **`void standbyMode()`**: use the STM32 Low Power library instead.
* **`uint8_t getAlarmMonth()`**
* **`uint8_t getAlarmYear()`**
* **`void setAlarmMonth(uint8_t month)`**
* **`void setAlarmYear(uint8_t year)`**
* **`void setAlarmDate(uint8_t day, uint8_t month, uint8_t year)`**

The following functions have been added to support specific STM32 RTC features:

_RTC hours mode (12 or 24)_
* **`void begin(RTCHourFormats_t format)`**

_RTC clock source_
* **`void setClockSource(sourceClock_t source)`** : this function must be called before `begin()`

_SubSeconds management_
* **`uint32_t getSubSeconds(void)`**
* **`void setSubSeconds(uint32_t subSeconds)`**

_Hour format (AM or PM)_
* **`uint8_t getHours(Hour12_AM_PM_t *format)`**
* **`void setHours(uint8_t hours, Hour12_AM_PM_t format)`**
* **`void setTime(uint8_t hours, uint8_t minutes, uint8_t seconds, uint32_t subSeconds, Hour12_AM_PM_t format)`**
* **`void setAlarmHours(uint8_t hours, Hour12_AM_PM_t format)`**
* **`uint8_t getAlarmHours(Hour12_AM_PM_t *format)`**
* **`void setAlarmTime(uint8_t hours, uint8_t minutes, uint8_t seconds, Hour12_AM_PM_t format)`**

_Week day configuration_
* **`uint8_t getWeekDay(void)`**
* **`void setWeekDay(uint8_t weekDay)`**
* **`void setDate(uint8_t weekDay, uint8_t day, uint8_t month, uint8_t year)`**

Refer you to the Arduino RTC documentation for the other functions  
http://arduino.cc/en/Reference/RTC

## Source

You can find the source files at  
https://github.com/stm32duino/STM32RTC
