.. _api-reference-label:

API Reference
=============

Common
^^^^^^^

.. _header-label:

* HTTP Request Header
  
    ==============  =======
    Request Header   Value 
    ==============  =======
    St2-Api-Key      Y2YyYWJkOGFkNDgxYTdiZDI0ZDdjNzU1NmE0NzA2ZWJiYTBlNTE5YmJlOTg1ODU0MzNmNjc3MzcxNDE0MDFhZA 
    content-type     application/json
    ==============  =======

    ``[NOTE] ask your system administrator for St2-Api-Key value for specific ITA deploay instance``

* API are all **Async**, unblock calls, which will return right away with task ID

* Use task ID to query task status via *HTTP GET*, for instance ::

    curl -k -H "St2-Api-Key: Y2YyYWJkOGFkNDgxYTdiZDI0ZDdjNzU1NmE0NzA2ZWJiYTBlNTE5YmJlOTg1ODU0MzNmNjc3MzcxNDE0MDFhZA" -H "content-type: application/json" https://192.168.1.212/api/executions/56a53236b29f785a86436d0c


SSH Adapter API
^^^^^^^^^^^^^^^

* Request Header, see :ref:`here <header-label>` 

* Request Method: **POST** 

* Request URL:  ``https://{IPAddress}/api/executions``

* Request Body

.. code-block:: json 

    {
      "action":"core.remote",
      "parameters": {
        "username":"root",  
        "password":"root",  
        "cmd":"df -h",      
        "timeout": 30,
        "hosts":"192.168.1.212"  
      }
    }    

* Parameters

    =========  =============  
    username   username to login to target system
    password   password to login to target system
    cmd        username to login to target system
    timeout    connection timeout in seconds 
    hosts      hosts seperated by commas
    =========  =============  


Local Commandline API
^^^^^^^^^^^^^^^^^^^^^

* Request Header, see :ref:`here <header-label>` 

* Request Method: **POST** 

* Request URL:  ``https://{IPAddress}/api/executions``

* Request Body

.. code-block:: json 

    {
      "action":"core.local",
      "parameters": {
        "cmd":"df -h",      
        "timeout": 30,
      }
    }    

* Parameters

    =========  =============  
    cmd        username to login to target system
    timeout    connection timeout in seconds 
    =========  =============  


HPSA rosh API
^^^^^^^^^^^^^

HPSA rosh API run remote command on target via HP Server Automation(HPSA) rosh utility, for details about rosh and HPSA, please refer to `HPSA officiall document <http://www8.hp.com/us/en/software-solutions/server-automation-software/>`_.

* Request Header, see :ref:`here <header-label>` 

* Request Method: **POST** 

* Request URL:  ``https://{IPAddress}/api/executions``

* Request Body

.. code-block:: json 

    {
      "action":"hpsa.rosh_py",
      "parameters": {
        "run_as_username": "root",
        "target_hostname": "vm001",
        "run_command": "df -h",
        "connection_timeout": 30
      }
    }    

* Parameters

    =================== ================================= 
    run_as username     user name to run remote command
    target_hostname     target server 
    run_command         command to run on target server 
    connection_timeout  connection timeout to ogfs server 
    =================== ================================= 


Task Result API
^^^^^^^^^^^^^^^

* Request Header, see :ref:`here <header-label>` 

* Request Method: **GET** 

* Request URL:  ``https://{IPAddress}/api/executions/{Task ID}``


