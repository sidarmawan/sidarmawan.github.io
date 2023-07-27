---
layout: post
title: "Get Detail Event Instance Openstack"
author: "Sidar"
categories:
    - Blog
tags:
    - Openstack
---

<p>This record is to display the details of each event instance openstack if there is an error in one of the events.</p>


<b>Server event list</b><br>
list recent event of instance <br>
```bash
openstack server event list <id-instance/name-instance>

example:
#openstak serve event list 2e3ffb9b-xxxxxxx-xxxxxxx-xxxxxxx
+------------------------------------------+--------------------------------------+--------+----------------------------+
| Request ID                               | Server ID                            | Action | Start Time                 |
+------------------------------------------+--------------------------------------+--------+----------------------------+
| req-bf970f56-9e42-460b-99ec-11cd71aabb28 | 2e3ffb9b-36b6-4013-b08f-b3cb43ce965f | create | 2020-03-05T06:27:58.000000 |
+------------------------------------------+--------------------------------------+--------+----------------------------+
```

<b>Server event show</b><br>
show detail server event<br>
```bash
openstack server event show <id-instance/name-instance> <request-id>

example:
#openstack server event show 2e3ffb9b-xxxxxxx-xxxxxxx-xxxxxxx req-bf970f56-9e42-460b-99ec-11cd71aabb28
+---------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Field         | Value                                                                                                                                                                              |
+---------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| action        | create                                                                                                                                                                             |
| events        | [{'event': 'compute__do_build_and_run_instance', 'start_time': '2021-06-05T06:28:01.000000', 'finish_time': '2020-03-05T06:28:08.000000', 'result': 'Success', 'traceback': None}] |
| instance_uuid | 2e3ffb9b-36b6-4013-b08f-b3cb43ce965f                                                                                                                                               |
| message       | None                                                                                                                                                                               |
| project_id    | a55axxxxxxxxxxxxxxxxxxxxxxxxxxxx                                                                                                                                                   |
| request_id    | req-bf970f56-9e42-460b-99ec-11cd71aabb28                                                                                                                                           |
| start_time    | 2020-03-05T06:27:58.000000                                                                                                                                                         |
| user_id       | 33b2a80xxxxxxxxxxxxxxxxxxxxxxxxx                                                                                                                                                   |
+---------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
```

source : https://docs.openstack.org/python-openstackclient/pike/cli/command-objects/server-event.html
