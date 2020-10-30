# fastcom

<div align="left">
<a href="https://ppizarror.com"><img alt="@ppizarror" src="https://img.shields.io/badge/author-Pablo%20Pizarro%20R.-lightgray.svg" /></a>
<a href="https://opensource.org/licenses/MIT/"><img alt="License MIT" src="https://img.shields.io/badge/license-MIT-blue.svg" /></a>
<a href="https://www.python.org/downloads/"><img alt="Python 3.4+" src="https://img.shields.io/badge/python-3.4+-red.svg" /></a>
<a href="https://pypi.org/project/pyfastcom"><img alt="PyPi package" src="https://badge.fury.io/py/pyfastcom.svg" /></a>
<br />
<a href="https://lgtm.com/projects/g/ppizarror/pyfastcom/alerts"><img alt="Total alerts" src="https://img.shields.io/lgtm/alerts/g/ppizarror/pyfastcom.svg?logo=lgtm&logoWidth=18" /></a>
<a href="https://lgtm.com/projects/g/ppizarror/pyfastcom/context:python"><img alt="Language grade: Python" src="https://img.shields.io/lgtm/grade/python/g/ppizarror/pyfastcom.svg?logo=lgtm&logoWidth=18" /></a>
<a href="https://github.com/ppizarror/pyfastcom/issues"><img alt="Open issues" src="https://img.shields.io/github/issues/ppizarror/pyfastcom" /></a>
<a href="https://pypi.org/project/pyfastcom/"><img alt="https://pypi.org/project/pyfastcom/" src="https://img.shields.io/pypi/dm/pyfastcom?color=purple" /></a>
</div><br />

API that lets get the results from fast.com test using Selenium.

## Install

pyfastcom can be installed via pip. Simply run:

```bash
pip install pyfastcom
```

## Usage

To create a searcher object, use the *PyFastCom* class:

```python
from pyfastcom import PyFastCom

fast = PyFastCom()
```

To configure the path of the webdriver (Chrome):

```python
fast.set_driver_path('path/to/webdriver/executable/')
```

Then, execute the `.run(timeout=120)` method. This function takes the timeout as an input. That is the maximum number of seconds before throwing an Exception. By default, the timeout is 240 s (2 minutes). The function returns the following dictionary:

```python
results = fast.run()
print(results) # {'client_ip': 'XXX', 'client_isp': 'XXX', 'client_location': 'XXX', 'download': (100, 'Mbps'), 'latency_download': (1, 'ms'), 'latency_upload': (1, 'ms'), 'server_info': 'XXX', 'upload': (100, 'Mbps')}
```

Also, the results can be obtained through the following methods:

- PyFastCom.*get_client_ip()*: Returns the client IP (str).
- PyFastCom.*get_client_isp()*: Returns the client ISP (str).
- PyFastCom.*get_client_location()*: Returns the client location (str).
- PyFastCom.*get_download_speed()*: Returns the download speed (int, str).
- PyFastCom.*get_download_latency()*: Returns the download latency (int, str).
- PyFastCom.*get_upload_speed()*: Returns the upload speed (int, str).
- PyFastCom.*get_upload_latency()*: Returns the upload latency (int, str).

Check out the provided example to see the complete usage scenario.
