i3
==

This role installs i3 + i3status and puts some config files for configured users on remote hosts.
It is possible to assemble one config file from serveral ones.

This role expects that the path to the home dir is /home/username

Requirements
------------

None

Role Variables
--------------

`i3_state`: State of i3 ("present" or "absent")

`i3_user_state`: State of i3 config for user ("present" or "absent", default: present)

`i3_user_config_multi`: If the user has more than one i3 config file ("yes" or "no", default: no)

`i3_user`: Array for users.

Dependencies
------------

None

Example Playbook
----------------

`some_host_var.yml`:

    i3_user:
    - name: foo
      i3config_multi: "yes" (when only one file, this can be absent or "no")
      i3config:
      - i3.base
      - i3.desktop (can also be only one file)
      i3status: status.desktop

`some_playbook.yml`:

    - hosts: with-x
      sudo: yes
      roles:
      - i3

License
-------

The MIT License (MIT)

Copyright (c) 2014 Julian Stiller

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Contributing
------------

I welcome contributed improvements and bug fixes via the usual github
workflow:

1. Fork this repository
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new pull request
