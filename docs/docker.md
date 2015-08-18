### some issue when using docker-py

- Using volumes:

    * Volumes declaration is done in two parts. Provide a list of mountpoints to the `Client().create_container()` method, and declare mapping in the `host_config` section.

    ```
    container = server.create_container(
        stdin_open=True, tty=True, detach=True, name="test", volumes="/data/maitai2/tools-automation", image="storage:0.1.0", command="/bin/bash", host_config=docker.utils.create_host_config(
            binds={
                '/data/':'/data/maitai2/tools-automation'
                })
    )
    ```

    * Default as 'rw' permission.

-------

## Using `create_container_from_config()` create container !!

    config = {
        'Hostname': hostname,
        'Domainname': domainname,
        'ExposedPorts': ports,
        'User': user,
        'Tty': tty,
        'OpenStdin': stdin_open,
        'StdinOnce': stdin_once,
        'Memory': mem_limit,
        'AttachStdin': attach_stdin,
        'AttachStdout': attach_stdout,
        'AttachStderr': attach_stderr,
        'Env': environment,
        'Cmd': command,
        'Dns': dns,
        'Image': image,
        'Volumes': volumes,
        'VolumesFrom': volumes_from,
        'NetworkDisabled': network_disabled,
        'Entrypoint': entrypoint,
        'CpuShares': cpu_shares,
        'Cpuset': cpuset,
        'CpusetCpus': cpuset,
        'WorkingDir': working_dir,
        'MemorySwap': memswap_limit,
        'HostConfig': host_config,
        'MacAddress': mac_address,
        'Labels': labels,
        'VolumeDriver': volume_driver,
    }

    set the config to what value you need.
