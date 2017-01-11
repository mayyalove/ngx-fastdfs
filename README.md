###install
        进入docker目录
        docker build -t  fastdfs:dev .
###使用
        docker -idt -p 80:80 fastdfs:dev /bin/bash
        进入容器执行
        /etc/rc.local
###测试
        进入容器执行test目录下的./test.sh或者直接执行下面脚本
        fdfs_test /etc/fdfs/client.conf upload /home/steven/01.jpg
        ...
        group_name=group1, ip_addr=192.168.1.181, port=23000
        storage_upload_by_filename
        group_name=group1, remote_filename=M00/00/00/wKgdhFTV0ZmAP3AZAPk-Io7D4w8580.jpg
        ...
        example file url: http://192.168.1.181/group1/M00/00/00/wKgdhFTV0ZmAP3AZAPk-Io7D4w8580.jpg
        storage_upload_slave_by_filename
        group_name=group1, remote_filename=M00/00/00/wKgdhFTV0ZmAP3AZAPk-Io7D4w8580_big.jpg
        ...
        example file url: http://192.168.1.181/group1/M00/00/00/wKgdhFTV0ZmAP3AZAPk-Io7D4w8580_big.jpg
 ###php调用
        首先进入php_client
        ./configure --with-php-config=/usr/local/php/bin/php-config
        make&&make install
        在php.ini里添加
        extension=fastdfs_client.so
        [fastdfs_client]
        fastdfs_client.base_path = /home/fastdfs/fastdfs
        fastdfs_client.connect_timeout = 2
        fastdfs_client.network_timeout = 60
        fastdfs_client.log_level = info
        fastdfs_client.log_filename =
        fastdfs_client.tracker_group_count = 1
        fastdfs_client.tracker_group0 = /etc/fdfs/client.conf
        fastdfs_client.use_connection_pool = true
        fastdfs_client.connection_pool_max_idle_time = 3600
        根据自己的情况做相应的修改
        重启php-fpm
        执行test目录下的fastdfs.php就可以看到效果了
###使用效果
![](https://github.com/qieangel2013/ngx-fastdfs/blob/master/images/cut.png)
###交流使用
	交流群：337937322
###如果你对我的辛勤劳动给予肯定，请给我捐赠，你的捐赠是我最大的动力
![](https://github.com/qieangel2013/zys/blob/master/public/images/pay.png)
[项目捐赠列表](https://github.com/qieangel2013/zys/wiki/%E9%A1%B9%E7%9B%AE%E6%8D%90%E8%B5%A0)
