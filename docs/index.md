# IoTaaP HAPI Documentation

!!! warning "Switching to IoTaaP OS"
    Please be aware that this library is deprecated and we have introduced IoTaaP OS from 2021-01-29, and for any new project
    we recommend using IoTaaP OS, although IoTaaP HAPI will still be available.
    [**IoTaaP OS is on GitHub**](https://github.com/iotaap/iotaap-os)

IoTaaP Hardware API is a special library that connects your Hardware with [IoTaaP Cloud Console](https://console.iotaap.io), just provide your credentials
and start transfering your data and controlling your device remotely. IoTaaP HAPI gives you the possibility to upgrade your devices firmware over the air (OTA).

## HAPI Reference

Our HAPI is object oriented C++ library made to be used with IoTaaP development hardware and PlatformIO ecosystem. HAPI easily integrates
with 3rd party libraries and resources in order to give you flexibility in development. 

!!! note "HAPI backward compatibility"
	HAPI might change in the future and you will be able to use specific library version by configuring it in platformio.ini library. 
    As our Hardware API library is community supported various performance, security and usability improvements are expected, and we
    are giving our best to ensure that the most recent versions are backward compatible. More info regarding `platformio.ini` configuration
    can be found [here](https://docs.platformio.org/en/latest/projectconf/section_env_library.html#lib-deps).