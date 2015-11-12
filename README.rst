CSV Scan
========

CSV scan is a simple tool for getting basic information about a csv document.

.. code-block:: python
   >>> doc = csv_scan.read('/path/to/csvfile.csv')
   >>> doc.columns
   ['name', 'age', 'occupation']
   >>> doc.details
   {'name': {'type': 'object', 'max_length': 20, 'has_null': False, 'num_null': 0, 'num_obs': 34210},
    'age': {'type': 'numeric', 'min': 2.0, 'max': 102.0, 'has_null': True, 'num_null': 20, 'num_obs': 34190},
    'occupation': {'type': 'object', 'max_length': 75, 'has_null': True, 'num_null': 9, 'num_obs': 34201}
   }
   >>> doc.info()
   # Information output here
...

It can also be used from the command line.

.. code-block:: bash
   $ csv_scan /path/to/csvfile.csv
   34210 observations, 3 fields, 2.4 mb
   $ csv_scan /path/to/csvfile.csv -v
   34210 observations

   Name        Num_obs     max_length     min     max     has_null     num_null
   ----        -------     ----------     ---     ---     --------     --------
   name        34210       20             -       -       False        0     
   age         34190       -              2.0     102.0   True         20
   occupation  34201       75             -       -       True         9

   Size: 2.4 mb
   Encoding: UTF-8
...

