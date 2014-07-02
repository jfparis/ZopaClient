ZopaClient
==========

Client library to access to the Zopa, peer to peer lending platform

# Installation

This module is available on PyPi so it can be installed by using the pip command

```
    pip install zopaclient
```

# Usage

```python
# -*- coding: utf-8 -*-

from __future__ import print_function, division, absolute_import
import zopaclient
from pprint import pprint

ZOPA_SECURITY = {
    "FIRST_SCHOOL": "xxx",
    "LAST_SCHOOL": "xxx",
    "PLACE_OF_BIRTH": "xxx"
}

def main():
    client = zopaclient.ZopaClient(email="myemail", password="password",
                            security_questions=ZOPA_SECURITY)
    client.connect()
    pprint(client.get_account_summary())


if __name__ == "__main__":
    main()

```

# Debugging

If something goes wrong you can enable debugging by adding the following lines at the beginning of you code
```python
logger = logging.getLogger('zopaclient')
logger.setLevel(logging.DEBUG)

ch = logging.StreamHandler()
formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
ch.setFormatter(formatter)
logger.addHandler(ch)
```