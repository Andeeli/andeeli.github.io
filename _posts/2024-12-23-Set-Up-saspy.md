---
title: "Installing SASPy Kernel for Jupyter"
description: >-
  This guide walks through the steps required to set up SASPy for use in Jupyter Notebooks and Jupyter Lab. By the end of this guide, you should be able to execute SAS code seamlessly from your Python environment.
author: 
date: 2024-12-23 12:00:00 +0000
categories: [Data Science, Programming Environment, IDE]
tags: [ide, sas, saspy, python, jupyter]
pin: false
mermaid: true
---

#### Prerequisites

1. **Install Jupyter Lab**
  ```bash
  pip install jupyterlab
  ```

2. **Install SASPy**
  ```bash
  pip install saspy
  ```

#### Configuration Steps

1. **Set the Configuration File for SASPy**
   - Copy a working example configuration file, such as `sascfg_personal.py`, and customize it for your setup. (An example is provided below.)
   - Ensure paths match your SAS installation

2. **Set the PATH Environment Variable**
   - Ensure SAS and related binaries are included in your system's PATH.
   - Update hosts file to resolve authentication issues:
     ```bash
    # In C:\Windows\System32\drivers\etc\hosts
    127.0.0.1 localhost view-localhost
    ```


#### Configuration Template

```python
# THIS IS AN EXAMPLE CONFIG FILE. PLEASE CREATE YOUR OWN sascfg_personal.py FILE USING THE APPROPRIATE TEMPLATES FROM BELOW
# SEE THE CONFIGURATION DOC AT https://sassoftware.github.io/saspy/install.html#configuration

SAS_config_names=['winlocal']

SAS_config_options = {'lock_down': False,
                      'verbose'  : True,
                      'prompt'   : True
                     }

SAS_output_options = {'output' : 'html5',       # not required unless changing any of the default
                      'style'  : 'HTMLBlue'}

default  = {'saspath'  : 'C:/Program Files/SASHome/SASFoundation/9.4/sas.exe'
            }

ssh      = {'saspath' : '/opt/sasinside/SASHome/SASFoundation/9.4/bin/sas_en',
            'ssh'     : '/usr/bin/ssh',
            'host'    : 'remote.linux.host',
            'encoding': 'latin1',
            'options' : ["-fullstimer"]
            }

# build out a local classpath variable to use below for Windows clients CHANGE THE PATHS TO BE CORRECT FOR YOUR INSTALLATION
cpW = "C:\\Program Files\\SASHome\\SASDeploymentManager\\9.4\\products\\deploywiz__94532__prt__xx__sp0__1\\deploywiz\\sas.svc.connection.jar"
cpW += ";C:\\Program Files\\SASHome\\SASDeploymentManager\\9.4\\products\\deploywiz__94532__prt__xx__sp0__1\\deploywiz\\log4j.jar"
cpW += ";C:\\Program Files\\SASHome\\SASDeploymentManager\\9.4\\products\\deploywiz__94532__prt__xx__sp0__1\\deploywiz\\sas.security.sspi.jar"
cpW += ";C:\\Program Files\\SASHome\\SASDeploymentManager\\9.4\\products\\deploywiz__94532__prt__xx__sp0__1\\deploywiz\\sas.core.jar"
cpW += ";C:\\ProgramData\\Anaconda3\\Lib\\site-packages\\saspy\\java\\saspyiom.jar"

iomlinux = {'java'      : '/usr/bin/java',
            'iomhost'   : 'linux.iom.host',
            'iomport'   : 8591,
            }

iomwin   = {'java'      : '/usr/bin/java',
            'iomhost'   : 'windows.iom.host',
            'iomport'   : 8591,
            }

winlocal = {'java'      : 'C:\\Program Files\\SASHome\\SASPrivateJavaRuntimeEnvironment\\9.4\\jre\\bin\\java.exe',
            'encoding'  : 'windows-1252',
            'classpath' : cpW
            }

winiomlinux = {'java'   : 'java',
            'iomhost'   : 'linux.iom.host',
            'iomport'   : 8591,
            }

winiomwin  = {'java'    : 'java',
            'iomhost'   : 'windows.iom.host',
            'iomport'   : 8591,
            }

winiomIWA  = {'java'    : 'java',
            'iomhost'   : 'windows.iom.host',
            'iomport'   : 8591,
            'sspi'      : True
            }

iomcom = {
    'iomhost' : 'mynode.mycompany.org',
    'iomport' : 8591,
    'provider': 'sas.iomprovider',
    'encoding': 'windows-1252'}

httpsviya = {'url'     : 'https://viya.deployment.com',
             'context' : 'Data Mining compute context',
             'authkey' : 'viya_user-pw',
             'options' : ["fullstimer", "memsize=1G"]
             }

httpviya = {'url'     : 'https://sastpw.rndk8s.openstack.sas.com:23456',
           #'port'    :  23456,   # can put different port here or ^ is it's not using the default port
            'context' : 'Data Mining compute context',
            'authkey' : 'viya_user-pw',
            'options' : ["fullstimer", "memsize=1G"]
            }

import os
os.environ["PATH"] += ";C:\\Program Files\\SASHome\\SASFoundation\\9.4\\core\\sasext\\sspiauth.dll"
os.environ["PATH"] += ";C:\\Program Files\\SASHome\\SASFoundation\\9.4\\core\\sasext"
```

#### Verification

Run the following Python code to confirm the setup:

```python
import saspy
import saspy.sascfg

sas = saspy.SASsession(cfgname='winlocal')
cars = sas.sasdata("CARS", "SASHELP")
cars.describe()
```

#### Troubleshooting
**Issue Encountered:** `"The application could not log on to the server 'localhost:0'. Integrated Windows authentication failed."`

**Solution:**

1. Refer to the SASPy troubleshooting documentation:
   - [SASPy Troubleshooting Guide](https://sassoftware.github.io/saspy/troubleshooting.html#iom-specific-errors)
   - [SAS Support Article](https://support.sas.com/kb/55/227.html)
2. Modify the hosts file:
   - Open the file located at `C:\Windows\System32\drivers\etc\hosts`.
   - Replace:
    ```bash
    127.0.0.1 view-localhost
    ```
    with:
    ```bash
    127.0.0.1 localhost view-localhost
    ```
