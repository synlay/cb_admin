ch_admin
=================

This is the admin interface for Chicago Boss, which can be configured as a standalone application with CB 0.6 or later.

Installation as a standalone server
-----------------------------------

Check your boss.config and make sure that the path's are correct, defaults to ../ChicagoBoss (framework) and ../cb_admin (the checkout dir).

Then:

    ./rebar compile
    ./init.sh start

Then visit http://localhost:8001/

Installation with an existing CB server
---------------------------------------

First "./rebar compile" and add the app config section to the boss.config of your existing CB server.

Add something like this to your boss.config:

    [{boss, [
        {applications, [cb_admin, ...]},
        ...
    ]},
    {cb_admin, [
        {path, "../cb_admin"},
        {allow_ip_blocks, ["127.0.0.1"]},
        {base_url, "/admin"}
    ]}].

