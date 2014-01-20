useradd Cookbook
================
Chef cookbook to create a custom user, add them to the "wheel" group, and populate authorized_keys

Requirements
------------
A databag named "users" needs to be created containing an object named for the user you will be adding. Within the object, place the following data;

{
  "name": "data_bag_item_users_someuser",
  "json_class": "Chef::DataBagItem",
  "chef_type": "data_bag_item",
  "data_bag": "users",
  "raw_data": {
    "id": "someuser",
    "key": "ssh-rsa AAAAB3NzaC1yc2E..."
  }
}

Attributes
----------
None

Usage
-----
Just include `useradd` in your node's `run_list`:

```json
{
  "name":"my_node",
  "run_list": [
    "recipe[useradd]"
  ]
}
```

Contributing
------------

1. Fork the repository on Github
2. Create a named feature branch (like `add_component_x`)
3. Write your change
4. Write tests for your change (if applicable)
5. Run the tests, ensuring they all pass
6. Submit a Pull Request using Github

License and Authors
-------------------
Authors: Darren Carpenter
