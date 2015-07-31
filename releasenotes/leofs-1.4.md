## 1.4.0-pre.1

### Features and Improvements for LeoFS

* New Features
    * AWS-Signature-v4 Support
        * Reference: [Authenticating Requests (AWS Signature Version 4)](http://docs.aws.amazon.com/AmazonS3/latest/API/sig-v4-authenticating-requests.html)
* Improvemens
    * Improved LeoFS's NFS performance
        * Retrieving list objects - *the ls and tree comand*
        * Copying objects
        * How to set up LeoFS's NFS feature:
            * [LeoFS with NFS](http://leo-project.net/leofs/docs/configuration/configuration_6.html)
        * Implemented LeoFS directory in [LeoStorage](https://github.com/leo-project/leo_storage) without degrading LeoStorage performance
            * [LeoFS directory's configuration](https://github.com/leo-project/leo_storage/blob/1.4.0-pre.1/priv/leo_storage.conf#L68-L75):
                * LeoFS Directory DB's directory: ``directory.db_path``
                * LeoFS Directory DB's container buffer: ``directory.cont_buffer_size``
                * LeoFS Directory DB's container expiration time: ``directory.cont_expiration_time``
    * [#283](https://github.com/leo-project/leofs/issues/283) ``leo_s3_libs`` Authenticating requests(AWS Signature version4) to be implemented
    * [#373](https://github.com/leo-project/leofs/issues/373) ``S3-API`` ``AWS-Signature-v4`` ``leo_gateway`` ``leo_s3_libs`` Support aws-sdk-go
    * [#375](https://github.com/leo-project/leofs/issues/375) ``NFS`` Reduce unnecessary round trips between nfs client and leo_gateway
    * [#400](https://github.com/leo-project/leofs/issues/400) ``all`` Use erlang:(max|min) if possible
    * [#403](https://github.com/leo-project/leofs/issues/403) ``s3-tests`` Increase s3-tests coverage

### Bugs Fixed

* [#370](https://github.com/leo-project/leofs/issues/370) ``s3-api`` ``leo_manager`` ``leo_gateway`` Return wrong http response when handling an invalid bucket format
* [#372](https://github.com/leo-project/leofs/issues/372) ``s3-api`` ``leo_gateway`` Return wrong http response when handling an invalid maxkeys parameter
* [#374](https://github.com/leo-project/leofs/issues/374) ``s3-api`` ``leo_gateway`` Return wrong http response when handling an invalid http headers
* [#381](https://github.com/leo-project/leofs/issues/381) ``leo_gateway`` Does not respond to "List Multipart Uploads" Operation
* [#401](https://github.com/leo-project/leofs/issues/401) ``leo_storage`` 500 error can occur under heavy load with N=1
* [#405](https://github.com/leo-project/leofs/issues/405) ``leo_object_storage`` Crashing ``leo_object_storage_server`` causes a corresponding leo_backend_db_server inaccessible
* [#406](https://github.com/leo-project/leofs/issues/406) ``leo_mq`` Crashing ``leo_mq_publisher`` causes a corresponding leo_backend_db_server inaccessible
* [#407](https://github.com/leo-project/leofs/issues/407) ``leo_ordning_reda`` ``add_container`` and ``remove_container`` can get into race condition

### Used Libraries

* Used libraries
    * leo project
        * [leo_backend-db v1.1.11](https://github.com/leo-project/leo_backend_db/releases/tag/1.1.11)
        * [leo_cache v0.6.7](https://github.com/leo-project/leo_cache/releases/tag/0.6.7)
        * [leo_commons v1.1.4](https://github.com/leo-project/leo_commons/releases/tag/1.1.4)
        * [leo_dcerl v0.4.0](https://github.com/leo-project/leo_dcerl/releases/tag/0.4.0)
        * [leo_logger v1.1.10](https://github.com/leo-project/leo_logger/releases/tag/1.1.10)
        * [leo_mcerl v0.6.0](https://github.com/leo-project/leo_mcerl/releases/tag/0.6.0)
        * [leo_mq v1.3.14](https://github.com/leo-project/leo_mq/releases/tag/1.3.14)
        * [leo_object_storage v1.3.0](https://github.com/leo-project/leo_object_storage/releases/tag/1.3.0)
        * [leo_ordning_reda v1.1.2](https://github.com/leo-project/leo_ordning_reda/releases/tag/1.1.2)
        * [leo_redundant_manager 1.9.17](https://github.com/leo-project/leo_redundant_manager/releases/tag/1.9.17)
        * [leo_rpc v0.10.5](https://github.com/leo-project/leo_rpc/releases/tag/0.10.5)
        * [leo_pod v0.6.4](https://github.com/leo-project/leo_pod/releases/tag/0.6.4)
        * [leo_s3_libs v1.2.1](https://github.com/leo-project/leo_s3_libs/releases/tag/1.2.1)
        * [leo_statistics v1.1.8](https://github.com/leo-project/leo_statistics/releases/tag/1.1.8)
        * [leo_watchdog v0.10.4](https://github.com/leo-project/leo_watchdog/releases/tag/0.10.2)
        * [savanna_agent v0.4.11](https://github.com/leo-project/savanna_agent/releases/tag/0.4.11)
        * [savanna_commons v0.8.14](https://github.com/leo-project/savanna_commons/releases/tag/0.8.14)
        * [erpcgen v0.2.3](https://github.com/leo-project/erpcgen/releases/tag/0.2.3)
        * [nfs_rpc_server v0.2.3](https://github.com/leo-project/nfs_rpc_server/releases/tag/0.2.3)
        * [leo_gateway v1.4.0-pre1](https://github.com/leo-project/leo_gateway/releases/tag/1.4.0-pre.1)
        * [leo_manager v1.4.0-pre1](https://github.com/leo-project/leo_manager/releases/tag/1.4.0-pre.1)
        * [leo_storage v1.4.0-pre1](https://github.com/leo-project/leo_storage/releases/tag/1.4.0-pre.1)
    * others
        * [bitcask v2.0.0](https://github.com/lbasho/bitcask/releases/tag/2.0.0)
        * [cowboy v1.0.0](https://github.com/leo-project/cowboy/releases/tag/1.0.0-p1)
        * [cowlib v1.0.0](https://github.com/extend/cowboy/releases/tag/1.0.0)
        * [elarm v0.3.0](https://github.com/leo-project/elarm/releases/tag/0.3.0)
        * [eleveldb v2.1.1](https://github.com/basho/eleveldb/releases/tag/2.1.1)
        * [folsom v0.8.2-for-leofs](https://github.com/leo-project/folsom/releases/tag/0.8.2-for-leofs)
        * [jiffy v0.13.3](https://github.com/davisp/jiffy/releases/tag/0.13.3)
        * [lz4 v0.2.2](https://github.com/leo-project/erlang-lz4/releases/tag/0.2.2)
        * [recon v0.8.5](https://github.com/ferd/recon/releases/tag/2.2.1)