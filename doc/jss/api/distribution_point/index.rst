Distribution Points
===================

.. automodule:: jss.distribution_point

.. inheritance-diagram:: jss.distribution_point
    :top-classes: jss.distribution_point.Repository


Architecture
------------

- **FileRepository** is the base class for all types of Distribution Point that require mounting.
- **DistributionServer** is the base class for all legacy Distribution Point types that used the dbfileupload API to upload
    and check for the existence of package(s).
- **CloudDistributionServer** is the base class for all newer Distribution Point types that upload directly to their cloud
    API counterparts.

Constructors
------------

Each class takes a **kwargs** object that describes the parameters needed for connection to the respective Distribution
Point. This varies greatly by the class that is being instantiated.

A general guide to some conventional parameters to **connection_args**::

    {
        'mount_point': '/path/to/mount/point',  # The mounted directory of an AFP or SMB share.
        'share_name': 'Share Name',  # Name of share mounted, may be used to construct mount URL.
        'url': 'dp.hostname',  # Hostname of the distribution point
        'port': 548,  # Port number of the distribution point
        'password': 'secret',  #  If the distribution point requires a mount password, set it here.
    }

**Requirements**:

- **AFP**: url, mount_point, username, password, share_name
- **SMB**: url, mount_point, username, password, share_name, domain
- **CDP** and **JDS**: jss


Classes
-------

.. toctree::
    :maxdepth: 2

    distribution_points.rst
    file_repository.rst
    mounted_repository.rst
    afp_dp.rst
    smb_dp.rst
    distribution_server.rst
    cdp.rst
    jds.rst
    jcds
    aws

