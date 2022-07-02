ECS
###

`ECS運用のノウハウ <https://qiita.com/naomichi-y/items/d933867127f27524686a>`__


ECSのログはそもそもデフォルトで出力されるようになっているので、設定ファイルを追加すれば良いだけっぽい！
そのため、`このページ <https://docs.aws.amazon.com/ja_jp/AmazonCloudWatch/latest/monitoring/create-cloudwatch-agent-configuration-file.html>`__
を参考にして設定ファイルを作成する。

`ここ <https://docs.aws.amazon.com/ja_jp/AmazonCloudWatch/latest/monitoring/download-cloudwatch-agent-commandline.html>`__
を参考に

``python:3.6`` のDockerを利用する場合は

.. code-block:: Dockerfile

    wget https://s3.amazonaws.com/amazoncloudwatch-agent/debian/amd64/latest/amazon-cloudwatch-agent.deb && \
        dpkg -i -E ./amazon-cloudwatch-agent.deb

を追記。

`Amazon ECS 細かい箇所を整理してみた  <https://qiita.com/leomaro7/items/6afd607f2df39f714a8e>`__

`ECSのノウハウ <https://www.slideshare.net/AmazonWebServicesJapan/aws-black-belt-online-seminar-2016-amazon-ec2-container-service>`__
