# puppet-modules-graph
Provides a tree view of Puppet Modules according to  Puppet's Roles-Profiles-Pattern

If you are using the [Roles-Profiles-Pattern](https://puppet.com/docs/pe/2017.2/r_n_p_intro.html) for assigning Puppet modules to you systems, you might be looking for a simple overview:

Which role includes which profiles? And which (leaf) modules are used in these profiles?

This little script looks for exactly these informations and displays a tree on the console.

Call the script without any parameters if your current working directory (cwd) is your modules directory. Otherwise give the path of your modules directory as the only parameter:

```Bash
~# ./puppet-modules-graph ~/puppet-modules

role::owncloud_server
|
+--profile::gallien_common
|      class 'gallien_default_users'
|      class 'openssh'
|      class 'trusted_certs' 
|      class 'send_nsca'
|
+--profile::owncloud_server
       class 'owncloud'

role::puppet_server
|
+--profile::gallien_common
|      class 'gallien_default_users'
|      class 'openssh'
|      class 'trusted_certs' 
|      class 'send_nsca'
|
+--profile::puppet_server
       class 'puppet_master'

[...]
```
