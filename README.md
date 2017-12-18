-   ![](https://anrisoftware.com/projects/attachments/download/217/apache2.0-small.gif)
    (© 2016 Erwin Müller)
-   [Source github.com](https://github.com/devent/apt_cacher_docker)
-   `git`anrisoftware.com:apt\_cacher\_docker.git@
-   `git`github.com:devent/apt\_cacher\_docker.git@

Description
===========

Installs the apt-cacher as a Docker container locally.  
After the installation, a Apt-proxy will be available at
`http://localhost:3142`  
The default cache directory will be `/var/cache/apt-cacher`

Usage
=====

Installation
------------

Installs the apt-cacher as a Docker container locally.

    make

Removes the apt-cacher container and all files.

    make clean

Apt-Proxy
---------

Add the Apt-proxy to your server.

    nano /etc/apt/apt.conf.d/01proxy

    Acquire::http::Proxy "http://:3142";

### Variables

<table>
<thead>
<tr class="header">
<th>Variable</th>
<th>Default</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PORTS</td>
<td>-p 3142:3142</td>
<td>The port that should be available for the proxy.</td>
</tr>
<tr class="even">
<td>CACHE_DIR</td>
<td>/var/cache/apt-cacher</td>
<td>The cache directory.</td>
</tr>
</tbody>
</table>

License
-------

This image is licensed under the
[MIT](https://opensource.org/licenses/MIT) license.

Copyright 2016-2017 Erwin Müller, erwin@muellerpublic.de

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
