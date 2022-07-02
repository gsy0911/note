AWS Batch
#########


`ここ <https://docs.aws.amazon.com/ja_jp/batch/latest/userguide/using_cloudwatch_logs.html>`__ にもあるように
``AWS Batch`` から ``CloudWatch Agent`` の設定は可能だと思う。

そして、 ``ecsInstanceRole`` にCloudWatchLogsへの権限を付与する。
付与して、CloudWatch Agentを開始せずに実行してみる。

AWS BatchからCloudWatchLogsに出力されるログストリームの名前の構成は

* ``{aws_batch_prefix}/default/{ecs_task_id}``
