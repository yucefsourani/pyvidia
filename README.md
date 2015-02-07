pyvidia
=======
Pyvidia is a script to detect the required driver series (and latest driver
version) for an NVIDIA graphics card in a Linux environment.

The script scrapes device and driver data from `nvidia.com`, so its device and
driver information are always up-to-date.

Inspired by the `nvidia-detect` utility in ELRepo:
http://elrepo.org/tiki/nvidia-detect

#Usage
Pyvidia can either be executed as a standalone script, or imported as a module
in other scripts.

##Script
When executing as a script, the default behavior is to return the required
driver series for the detected NVIDIA device.

The following command line options are also available:
```
--latest                Output the latest version number of the driver for the
                        detected NVIDIA device

--series                Output the required driver series for the detected
                        NVIDIA device [Default]

--deviceid DEVICEID     Provide a device PCI ID to be used instead of auto-
                        detecting one
```

##Import
When imported into another script, there are several available functions:

```
get_required_driver_series(device_id)
    Returns the required driver series for the given or detected NVIDIA device.

    Keyward Args:
    device_id - The device PCI ID to check against the supported devices lists
```

```
get_latest_driver_version(device_id)

    Keyward Args:
    device_id - The device PCI ID to check against the supported devices lists
```

```
get_nvidia_device_id()
    Returns the device ID of the detected NVIDIA device, or none if one is not
    present.
```

```
get_all_supported_devices()
    Returns a dictionary keyed by driver series number, containing the latest
    driver version number and a list of supported devices for that series.
```

#Requirements
The required modules for this script can be installed via pip:
```
pip install -r requirements.txt
```