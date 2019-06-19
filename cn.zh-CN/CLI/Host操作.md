# Host操作 {#concept_189194 .concept}

host操作目前只支持ssh登录目标机器，exec在目标机器上执行命令。

-   wpctl ssh：需要用户在环境所在的安全组里有一台跳板机，用户可以选择其中一台ECS，或者单独创建一台broker。

    ``` {#codeblock_7zc_ge5_b3g}
    $ wpctl configure
    Configuring profile 'default' in '' authenticate mode...
    Access Key Id [*************zGQ]:
    Access Key Secret [***************************N91]:
    Default Region Id [cn-shenzhen]:
    Default Output Format [json]: json (Only support json))
    Default Language [zh|en] zh:
    
    Configuring broker options...
    Broker Address [120.79.86.15]: 47.112.30.3
    Broker Port [22]:
    Broker User [root]:
    Broker Password [********4]:
    Broker Identity File []:
    
    Saving profile[default] ...Done.
    Configure Done!!!
    
    $ webxctl ssh demo-test-1
    [\] Finding servers of demo-test-1] (1s)
    [OK] Finding servers of demo-test-1 (2s)
    Found 2 servers:
    +----+------------------------+----------------+---------------+---------------+---------+
    | NO |           ID           |   PRIVATE IP   |   HOSTNAME    |   PUBLIC IP   | STATUS  |
    +----+------------------------+----------------+---------------+---------------+---------+
    |  1 | i-wz9i4zv4ov7fktngxefv | 172.18.207.215 | document-test | 47.112.30.3   | Running |
    |  2 | i-wz9i6yrcr8jgkurozbzi | 172.18.207.217 | document-test | 39.108.254.90 | Running |
    +----+------------------------+----------------+---------------+---------------+---------+
    Please choose server to operate [1]: 2
    
    
    [OK] Testing connection bewteen broker and server (0s)
    [OK] Adding auth key to 172.18.207.217 through CA (4s)
    [OK] Start forwarding on: [ 127.0.0.1:58424 -> 172.18.207.217:22 ] (0s)
    
    
    
    ****************************************
    * Logged on 172.18.207.217 as root     *
    ****************************************
    Last login: Tue Apr 23 15:14:52 2019 from 106.11.235.191
    
    Welcome to Alibaba Cloud Elastic Compute Service !
    
    [root@iZwz9i6yrcr8jgkurozbziZ ~]#
    ```

-   wpctl exec：选择环境中的机器执行命令,多个实例存在时需要选择机器, 此功能需要安装云助手。

    ``` {#codeblock_dde_yvo_ey8}
    $ wpctl env:exec demo-test-1 'echo hello'
    [OK] (1s)ng servers of demo-test-1
    [OK] Finding servers of demo-test-1 (2s)
    Found 2 servers:
    +----+------------------------+----------------+---------------+---------------+---------+
    | NO |           ID           |   PRIVATE IP   |   HOSTNAME    |   PUBLIC IP   | STATUS  |
    +----+------------------------+----------------+---------------+---------------+---------+
    |  1 | i-wz9i4zv4ov7fktngxefv | 172.18.207.215 | document-test | 47.112.30.3   | Running |
    |  2 | i-wz9i6yrcr8jgkurozbzi | 172.18.207.217 | document-test | 39.108.254.90 | Running |
    +----+------------------------+----------------+---------------+---------------+---------+
    Please choose server to operate [default:1] [0 for all instances]:
    [OK] Checking Cloud Assistant status of 1 servers (1s)
    [OK] Executing Commands on 1 servers (3s)
    >>>>> 172.18.207.215 [i-wz9i4zv4ov7fktngxefv] status:Finished >>>>>
    hello
    
    <<<<< -----
    ```


